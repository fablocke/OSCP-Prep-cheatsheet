# Scanning 
### NMAP TCP quick 

sudo nmap -Pn -v -sS -sV -sC -oN tcp-quick.nmap IP

### NMAP TCP Full 

sudo nmap -Pn -sS --stats-every 3m --max-retries 1 --max-scan-delay 20 --defeat-rst-ratelimit -T4 -p1-65535 -oN tcp-full.nmap IP 

### NMAP TCP - Repeat if extra ports found 

sudo nmap -Pn -v -sS -A -oN tcp-extra.nmap -p PORTS IP 

### NMAP UDP quick 

sudo nmap -Pn -v -sU -sV -oN udp-quick.nmap IP

### NMAP UDP 1000 

sudo nmap -Pn --top-ports 1000 -sU --stats-every 3m --max-retries 1 -T4 -oN udp-1000.nmap IP

### NMAP UDP - Repeat if extra ports found 

sudo nmap -Pn -sU -A -oN udp-extra.nmap -p PORTS IP 

# Enumeration 

### FTP - Port 21 
Check for FTP version vulns
Check for Anonymous login 
Check for Read access
Check for Web root or root directories of any other accessible service 
Check for write access 

### SSH - Port 22 
Check for SSH version vulns
Check for User enumeration if necessary 

### DNS - Port 53 
Might indicate a domain controller on Windows 
Check for zone transfer - 

### Kerberos - Port 88 
Indication that its a DC 

### Netbios - Port 139 
> nbtscan IP 

### RPC - PORT 135 
> sudo nmap -sS -Pn -sV --script=rpcinfo.nse -p135 0 

### LDAP - Ports 389,636,3268,326
> sudo nmap -sS -Pn -sV --script=ldap* -p389,636,3268,3269  

### SMB - Ports 
> sudo nmap -Pn --script=smb-proto* -p139,445 
> sudo nmap -Pn --script=smb-os-discovery.nse -p139,445
> sudo nmap -Pn --script=smb-enum* -p139,445
> sudo nmap -Pn --script=smb-vuln* -p139,445
