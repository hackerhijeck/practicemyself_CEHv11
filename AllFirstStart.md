### 1. Find the IP target.
  $ ip addr
  
### 2. Nmap scan all
  $ nmap IP -sV -sC -p -O
  
### 3. IPs Service, RDP(3389), SQL(3306), FTP(21) check
 ```
  $ nmap -Pn -p 3389 IP | grep open
  $ nmap -Pn -p 3306 IP | grep open
  $ nmap -Pn -p 21 IP | grep open
  ```
### 4. Windows Comman Line
  $ Net user

### 5. WP scan (Wp Vulnerability)
  $ wpscan --url IP --enumerate u
```  
 => msfconsole 
use axiliary/scanner/http/wordpress_login_enum
PASS_FILE /root/Desktop/wordlists/Pass.txt
set RHOSTs IP
set RPORT PORT
set TARGETURI http://IP:port
set USERNAME admin
->run
```
### 6. FTP Passowrd find
  $ hydra -l user -P passlist.txt ftp://IP

### 7. Prints the route that a packet takes to reach the host
  $ traceroute google.com

### 8. Android
```
  $ netdiscover -r IP/24   (got final IP)
  $ nmap -O IP
```

### 9. Stegography
  ```
  $ Snow.exe -C -p “given_password” file_name.txt
  -C  compressing / uncompressing
  -p  password

  Open Stego 
  GUI tool
  ```

## 10. Used Tools
```
Veracrypt
Cryptool
Snow
Bctextencoder
Md5 & sha1 checksum utility
Wpscan
Nmap
Metasploit
Hydra
Wireshark
Winscp
OWASP ZAP  
RDP
```
