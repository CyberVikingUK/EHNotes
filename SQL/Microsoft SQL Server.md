impacket -> mssqlclient.py

You can connect to a Microsoft SQL Server with myssqlclient.py knowing a username and password like so:
`mssqlclient.py username@10.10.10.125`
It will prompt you for a password. If your password fails, the server might be using "Windows authentication", which you can use with:
`mssqlclient.py username@10.10.10.125 -windows-auth`

If you have access to a Micosoft SQL Server, you can try and enable_xp_cmdshell to run commands. With mssqlclient.py you can try:
`SQL> enable_xp_cmdshell`
though, you may not have permission. If that DOES succeed, you can now run commands like:
`SQL> xp_cmdshell whoami`
