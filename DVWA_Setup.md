## DVWA Set up with kali linux:

### Method 1
#### In linux root:
```
$ cd /var/www/html
$ git clone https://github.com/digininja/DVWA 
$ mv DVWA dvwa (if u want)
$ chmod -R 777 dvwa
$ cd dvwa/config
$ cp config.inc.php.dist config.inc.php
$ nano config.inc.php (change the default user and password to "admin" and "password")
$ service mysql start (start mysql server)
$ mysql -u root
$ create database dvwa
$ create user 'admin'@'127.0.0.1' identified by 'password';
$ grant all privileges on dvwa.* to 'admin'@'127.0.0.1'; 
$ service start apache2
$ nano /etc/php/8.1/apache2/php.ini

  Ctrl+w type "fopen" and change the "off" to "on"  (allow_url_include = on)
```
### Method 2
#### In linux root:
```
$ cd /var/www/html
$ git clone https://github.com/digininja/DVWA
$ mv DVWA dvwa
$ chown -R www-data:www-data dvwa
$ cd dvwa/config
$ cp config.inc.php.dist config.inc.php
$ nano config.inc.php
	change the user name and password
$ sudo service mysql start
$ mysql -u root
	CREATE DATABASE dvwa;
	CREATE USER 'admin'@'127.0.0.1' IDENTIFIED BY 'password';
	GRANT ALL PRIVILEGES ON dvwa.* TO 'admin'@'127.0.0.1';
$ service apache2 start
$ nano /etc/php/8.2/apache2/php.ini
  Ctrl+w type "fopen" and change the "off" to "on"  (allow_url_include = on)
```
