
Use the * wildcard to scan an entire subnet at once.
```bash
nmap 192.168.0.1,2,3
nmap 192.168.0.1-4
nmap 192.168.0.* --exclude 192.168.0.2
nmap 192.168.0.* --excludefile /file.txt
```
Scans all reserved TCP ports on the machine `scanme.nmap.org`:
```bash
nmap -sS -O scanme.nmap.org
```

Launches a stealth SYN scan against each machine that is up out of the 256 IPs on the /24 sized network
```bash
nmap -sV -p 22,53,110,143,4564 198.116.0-255.1-127
```

```bash
nmap -Pn -O -v scanme.nmap.org
```

Also enable scripts, service detection, OS fingerprinting and traceroute:
```bash
nmap -A scanme.nmap.org
```

Scan for All TCP Ports:
```bash
nmap -sT scanme.nmap.org
```

Scan for All UDP Ports:
```bash
nmap -sU scanme.nmap.org
```

Perform a Fast Scan
```bash
nmap -F scanme.nmap.org
```

Display the Reason why Nmap thinks that a port is in a particular state:
```bash
nmap --reason scanme.nmap.org
```

## Local scan with MAC address spoofing

Spoof your MAC Address:
```bash
nmap --spoof-mac 01:23:45:667:89:ab 192.168.0.13
```

Spoof your MAC Address with a Random MAC:
```bash
nmap --spoof-mac 0 192.168.0.13
```

## NMAP Heartbleed vulnerability scan
```bash
nmap -d --script ssl-heartbleed --script-args vulns.showall -sV X.X.X.X/24
```
Options summary:

* `-d turns` on debugging output, helpful for seeing problems with the script.
* `--script` ssl-heartbleed selects the ssl-heartbleed script to run on appropriate ports.
* `--script-args` vulns.showall tells the script to output "NOT VULNERABLE" when it does not detect the vulnerability.
* `-sV` requests a service version detection scan, which will allow the script to run against unusual ports that support SSL.
