# practicemyself
CEH Practical Important Notes

I'm Preparing CEH Practical V11. hope it will be help full to all of you guys. If any suggetions to me just connect with twitter and dm me. Thank You.

## CEH Practical Contents:
1.
2.
3.
4.
5.
6.
7.
8.
9.
10
11.
12.
14.
15.

## Important Tools and Commands:
1. Nmap:
  $ nmap -sV -sC -O <IP>
  
  -iL = import txt  -oX = output   --top-ports 1000 = UDP 1000 scan   -sU = UDP scan   -sT = TCP scan 
  
2. SQLmap
  for url= -u
  for txtfile= -r
  $ sqlmap -r test.txt --batch --risk 3 --level 4 --dbs
  $ sqlmap -r test.txt --batch --risk 3 --level 4 -D databasename --tables
  $ sqlmap -r test.txt --batch --risk 3 --level 4 -D databasename -T tables name --dump

3. WPscan
  $ wpscan --url http://test.com --enumerate u --enumerate p
  $ wpscan --url http://test.com --usernames user.txt --passwords pass.txt
  
  Other Commands: --random-agent, 

4. Hydra
  FTP Bruteforce:
  $ hydra -l user -P passlist.txt ftp://IP

  SSH Bruteforce:
  $ hydra -l <username> -P <full path to pass> IP -t 4 ssh

  Post Web Form Bruteforce:
  for single word= -l, -p
  for txt file= -L, -P
  $ hydra -l <username> -P <wordlist> IP http-post-form "/loginUrl:username=^USER^&password=^PASS^:F=incorrect" -V

5. John the Ripper
  $ john -format=raw-md5 hash.txt
  $ john -format=<hashformat> hash.txt
  
6. SSH
  SSH connect:
  $ ssh <username>@IP
  
7. FTP
  FTP Connect
  $ ftp IP

## SQL Injection Payloads:


