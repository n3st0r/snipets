
Use the * wildcard to scan an entire subnet at once.
```
nmap 192.168.0.1,2,3
nmap 192.168.0.1-4
nmap 192.168.0.* --exclude 192.168.0.2
nmap 192.168.0.* --excludefile /file.txt
```
Scans all reserved TCP ports on the machine `scanme.nmap.org`:
```bash
nmap -sS -O scanme.nmap.org/24
```

Launches a stealth SYN scan against each machine that is up out of the 256 IPs on the /24 sized network
```
nmap -sV -p 22,53,110,143,4564 198.116.0-255.1-127
```

```
nmap -Pn -O -v scanme.nmap.org
```

Also enable scripts, service detection, OS fingerprinting and traceroute:
```
nmap -A scanme.nmap.org
```

Scan for All TCP Ports:
```
nmap -sT scanme.nmap.org
```

Scan for All UDP Ports:
```
nmap -sU scanme.nmap.org
```

Perform a Fast Scan
```
nmap -F scanme.nmap.org
```

Display the Reason why Nmap thinks that a port is in a particular state:
```
nmap --reason scanme.nmap.org
```

## Local scan with MAC address spoofing

Spoof your MAC Address:
```
nmap --spoof-mac 01:23:45:667:89:ab 192.168.0.13
```
Spoof your MAC Address with a Random MAC:
```
nmap --spoof-mac 0 192.168.0.13
```
