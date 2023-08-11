SMBMap tells you permissions and access, which smbclient does not do!

To try and list shares as the anonymous user DO THIS (this doesn't always work for some weird reason)
`smbmap -H 10.10.10.125 -u anonymous`

Or you can attempt just:
`smbmap -H 10.10.10.125`

And you can specify a domain like so:
`smbmap -H 10.10.10.125 -u anonymous -d HTB.LOCAL`

Worth trying localhost as a domain, if that gets "NO_LOGON_SERVERS"
`smbmap -H 10.10.10.125 -u anonymous -d localhost`
