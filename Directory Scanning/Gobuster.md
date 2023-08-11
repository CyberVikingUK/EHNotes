For searching for extra directories in the Terminal
`gobuster dir -u http://10.10.10.28 -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt`

To look for files, add `-x sh,cgi,log,html,php,http,zip,txt` etc, after dir

DNS Scan:
`gobuster dns example.com -w /opt/useful/SecLists/Discovery/DNS/subdomains-top1million-5000.txt`
