You may need to convert the hash into a format that John can work with e.g. an id_rsa file:
`ssh2john id_rsa > id_rsa.hash`

`john -w=/usr/share/wordlists/rockyou.txt id_rsa.hash`
