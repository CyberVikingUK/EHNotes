Downloading file from SSH
`scp <username>@<IP address>:~/file/directory/filename.txt /destination/directory`

Example: 
`scp remnux@10.10.135.248:~/Tasks/3/notavirus.pdf /root/`


On local machine:
`nc -lvnp <port> > <what_to_call_file>`
e.g.
`nc -lvnp 9500 > sus.pcapng`
