Standard Scan
`nmap -sV -O -A -v 10.10.10.10`

Quick all Ports scan
`nmap -p- --min-rate=10000 -v 10.10.10.10`

UDP Scan
`nmap -sU 10.10.10.10`
`nmap -sUV -T4 -F --version-intensity 0 10.10.10.10`
can use –min-rate 10000

Standard Operators:
•	-sV = Service Version
•	-O = Operating System
•	-A = All extra information
•	-v = Verbose (displays progress)

Optional Operators:
•	-p- = Scans all ports (time consuming)
•	-F = 100 most common ports
•	-oN filename.txt = Saves output to text file
•	-sC = Runs all extra scripts (heavier info grab)
•	--script=vuln = Scans for vulnerabilities
•	-T0-5 = 0-Paranoid (5mins between sends), 5-Very fast
