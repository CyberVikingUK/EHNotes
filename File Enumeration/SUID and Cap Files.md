**Find SUID Files**
`find / -user <username> -perm -4000 -print 2>/dev/null`
or
`find / -perm -u=s -type f 2>/dev/null`
or
`find / -type f -user root -perm -4000 -exec ls -ldb {} \; 2>/dev/null`
^ finds all suid files that can be run as root

**Capability set files**
`getcap -r / 2>/dev/null`

Add -ls to see permissions

**Exploit SUID Files**
Use [GTFOBins](https://gtfobins.github.io/) and search for the suspect ones e.g. usr/bin/python
REMOVE THE ./ FROM THE START OF THE CODE!
