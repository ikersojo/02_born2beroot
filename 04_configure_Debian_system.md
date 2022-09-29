# Configure the Debian System
## Hostname
Show hostname:
```console
hostnamectl status
```
All is included in files.They can be manually modified or using a command.
- Manual mod:
```console
sudo nano /etc/hostname
sudo nano /etc/hosts
```
- Commnad:
```console
sudo hostnamectl set-hostname **new_host_name**
```
## AppArmor
AppArmor is a security program for Linux distributions that allows a system administrator to rescrict a program’s access to the operating system. Each program has an associated profile that controls its ability to access the network, its read, write and execution permissions, among other things. AppArmor came preinstalled in Debian.

AppArmor tends to allow everything and then gradually restrict, whereas SELinux in CentOS starts off by restricting everything, and then loosening up little by little. Other difference: SELinux applies labels to each file, whereas AppArmor monitors software paths.
### Check AppArmor is running:
```console
sudo aa-status
```

## sudo
The sudo command allows to run programs with the security privileges of another user (by default, as the superuser). It prompts for your user password and confirms the request to execute a command by checking a file, called sudoers, which the system administrator configures.
### Install sudo
- Login as “root”
- Install sudo
```console
apt install sudo
```
- Add user to sudo group:
```console
usermod -aG sudo **username**
```
- NOTE: we can create more user by using the command:
```console
sudo useradd **username**
```
- Check that the user is in the sudo group:
```console
getent group sudo
```
- Reboot
```console
reboot
```
### Configure sudo
- Login as “**username**”
- Create a sudo configuration file:
```console
sudo nano /etc/sudoers.d/sudoconfig
```
- Edit the document with the following content:
```console
Defaults	passwd_tries=3
Defaults	badpass_message="Wrong Password. Keep calm and keep trying!"
Defaults	logfile="/var/log/sudo/sudo.log"
Defaults	log_input,log_output
Defaults	iolog_dir="/var/log/sudo"
Defaults	requiretty/
Defaults	secure_path="/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/snap/bin"
```

## SSH and Firewall
SSH, or Secure Shell, is a network protocol that allows us to connect to a computer from a distance, over an unsecured network. Thanks to user passwords and the creation of public and private keys, the data communicated from one computer to the other is encrypted.
### Install and configure SSH Server
- Install openssh server:
```console
sudo apt install openssh-server 
```
- Edit ssh config file:
```console
sudo nano /etc/ssh/sshd_config
```
	- “# Port 22” to “Port 4242” (uncomment and change port)
	- “# PermitRootLogin prohibit-password” to “PermitRootLogin no”
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/config1.png\?raw\=true">
- Reboot
```console
sudo reboot
```
- Check status (focus on port 4242):
```console
systemctl status ssh
```
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/config2.png\?raw\=true">
### Install and configure UFW firewall
- Install openssh server:
```console
sudo apt install ufw
sudo ufw enable
sudo ufw allow 4242
sudo ufw status
```
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/config3.png\?raw\=true">
- Get and write down ip address:
```console
ip a s
```
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/config4.png\?raw\=true">
### Check SSH conection
- Go to host mac terminal
```console
ssh isojo-go@ip-address -p 4242
```
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/config5.png\?raw\=true">
- If everything is fine, logout and close:
```console
logout
exit
```

## User Management
### Create new group
- Create group:
```console
sudo addgroup user42
```
Check the correct creation of the group:.
```console
getent group user42
```
Add user to group:
```console
sudo usermod -aG user42 isojo-go
```
### Create/Delete/Check users
- Create new user:
```console
sudo adduser **username**
```
- List users:
```console
less /etc/passwd
```
- Modify username:
```console
usermod –l **new_name** old_username
```
- Delete user:
```console
sudo userdel **user_name**
```
- Check the information of the password of a user:
```console
sudo chage -l **username**
```
### Configure users passwords
- Go to passwords config file
```console
sudo nano /etc/login.defs
```
- Modify the following parameters:
	- “PASS_MAX_DAYS 99999” to “PASS_MAX_DAYS 30”
	- “PASS_MIN_DAYS 0" to “PASS_MIN_DAYS 2”
	- Keep "PASS_WARN_AGE 7"
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/config6.png\?raw\=true">
- For the user generated during install and root, it does not update the password policies. To do so, force manually:
```console
sudo chage -m 2 -M 30 isojo-go
sudo chage -m 2 -M 30 root
``` 
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/config9.png\?raw\=true">
- Install password quality management package (PAM (Pluggable Authentication Modules):
```console
sudo apt install libpam-pwquality
```
- Configure password strength:
```console
sudo nano /etc/pam.d/common-password
```
Append to "password requisite pam_pwquality.so retry=3" line the following:
- password   requisite   pam_pwquality.so retry=3 **minlen=10 ucredit=-1 dcredit=-1 repeat=3 reject_username difok=7 enforce_for_root**

Detail of each flag:
- minlen=10 (minimum 10 characters of length)
- ucredit=-1 dcredit=-1	(at least 1 upper and digit)
- maxrepeat=3 (maximum 3 consecutive identical chararcters)
- reject_username (username cannot be included in the password)
- difok=7 (at least 7 characters are modified from the previous password)
- enforce_for_root (root password has the same requirements)

### Change user Password
```console
passwd isojo-go
passwd root
```