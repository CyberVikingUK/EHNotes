Find out what version of Python is installed `which python` or `which python3` (usually python3)
Run `python3 -c 'import pty;pty.spawn("/bin/bash")'` this sets up a better shell
Run `export TERM=xterm` this gives access to term commands like clear
Background the shell with **CTRL + z**
Run `stty raw -echo; fg` this gives access to arrow keys, tab autocomplete etc and brings the shell to the foreground again
