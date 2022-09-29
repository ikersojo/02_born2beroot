# Setup Linux Lighttpd MariaDB PHP (LLMP)
## What is LLMP?
Lighttpd is a  secure, fast and flexibly HTTP server with a small memory footprint compared to other web-servers. Its event-driven architecture is optimized for a large number of parallel connections (keep-alive) which is important for high performance dynamic applications.

WordPress, the most powerful and popular content management systems (CMS) is the right tool to develop and build powerful and dynamic websites based on PHP is flexible and can be run on variety or HTTP servers.
## Install LLMP
Install LLMP and allow firewall
```console
sudo apt install lighttpd
sudo ufw allow 80
sudo ufw status
```
## Install and configure MariaDB
Install MariaDB Database Server
```console
sudo apt install mariadb-server
```
Secure MariaDB server
```console
sudo mysql_secure_installation
```
- Enter current password for root (enter for none): Just press the Enter
- Switch to unix_socket authentication [Y/n] n
- Change root password? [Y/n]: n
- Remove anonymous users? [Y/n]: Y
- Disallow root login remotely? [Y/n]: Y
- Remove test database and access to it? [Y/n]:  Y
- Reload privilege tables now? [Y/n]:  Y

Restart MariaDB server
```console
sudo systemctl restart mysql.service
```
Login in MariaDB Shell:
```console
sudo mariadb
```
Create database and user, and grant the user the privileges.
```console
CREATE DATABASE wordpress_db;
CREATE USER 'isojo-go'@localhost IDENTIFIED BY 'bor2beROOT';
GRANT ALL ON wordpress_db.* TO 'isoo-go'@'localhost' IDENTIFIED BY 'born2beROOT' WITH GRANT OPTION;
FLUSH PRIVILEGES;
exit
```
Check user by connecting to mariabd
```console
mariadb -u nombre_usuario -p
```
```console
SHOW DATABASES;
exit
```
## Install and configure PHP
```console
sudo apt install php-cgi php-mysql
```
## Install and configure WordPress
```console
sudo apt install wget
sudo wget http://wordpress.org/latest.tar.gz
sudo tar -xzvf latest.tar.gz
sudo mv wordpress/* /var/www/html/
sudo rm -rf latest.tar.gz wordpress/
sudo cp /var/www/html/wp-config-sample.php /var/www/html/wp-config.php
```
Link Wordpress to MariaDB
```console
sudo nano /var/www/html/wp-config.php
```
Replace:
- define( 'DB_NAME', 'wordpress_db' );
- define( 'DB_USER', 'isojo-go' );
- define( 'DB_PASSWORD', 'born2beROOT' );
- define( 'DB_HOST', 'localhost' );

Change the permissions for the WordPress directories for the www-data user (our web server) and restart lighttpd:
```console
sudo chown -R www-data:www-data /var/www/html/
sudo chmod -R 755 /var/www/html/
sudo systemctl restart lighttpd
```

## Activating FastCGI
FastCGI (Fast Common Gateway Interface) is a binary protocol that allows a web server to interact with external application, in our case, PHP. We need to set up this protocol between lighttpd and PHP in order to be able to access our info.php page from a web browser.FastCGI (Fast Common Gateway Interface) is a binary protocol that allows a web server to interact with external application, in our case, PHP. We need to set up this protocol between lighttpd and PHP in order to be able to access our info.php page from a web browser.

Enable the follwoing modules:
```console
sudo lighty-enable-mod fastcgi
sudo lighty-enable-mod fastcgi-php
sudo service lighttpd force-reload
```

## Check Service
Go to ip adress in a web browser (on host mac): 

# Setup File Transfer Protocol (FTP)
## Install FTP
```console
$ sudo apt install vsftpd
```

Allow conxions through port 21:
```console
$ sudo ufw allow 21
```

Configure root folder for the user (/home/usuario/ftp):
```console
sudo mkdir /home/usuario/ftp
sudo mkdir /home/usuario/ftp/files
sudo chown nobody:nogroup /home/usuario/ftp
sudo chmod a-w /home/usuario/ftp
```

Configure vsftpd:
```console
$ sudo nano /etc/vsftpd.conf
```
- uncomment: #write_enable=YES
- uncomment: #chroot_local_user=YES
- 
Paste at the very end:
```console
user_sub_token=$USER
local_root=/home/$USER/ftp
userlist_enable=YES
userlist_file=/etc/vsftpd.userlist
userlist_deny=NO
```

Whitelist FTP:
```console
sudo touch /etc/vsftpd.userlist
echo isojo-go | sudo tee -a /etc/vsftpd.userlist
```

##Connect to server using FTP
Go to the follwoing URL on host mac using a web browser (do not use Safari):
- ftp://<ip-address>
- Open in finder
- Enter FTP user and password
End session using CTRL + D.
	
To check the ftp server, go to ftp://<ip-address>:21 and enter user and password.
