# Introduction
- For this project, you have to clone their Git repository on **their station**.
## Auxialiary Info
- encryption key: **passWORD123**
- root password: **born2beROOT**
- user (password): **isojo-go** (**born2beROOT**)

# Mandatory Part
## Check Delivered work
- [x] Ensure that the "signature.txt" file is present at the root of the cloned repository.
- [x] Check that the signature contained in "signature.txt" is identical to that of the ".vdi" file of the virtual machine to be evaluated.
```console
shasum xxx.vdi
```
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/def1.png\?raw\=true">

- As a precaution, you can **duplicate** the initial virtual machine in order to keep a copy.
- Then, start the virtual machine to be evaluated.

## Project overview
During the defense, a script must display information allevery 10 minutes. Its operation will be checked in detail later.
The student being evaluated should explain to you simply:
- [x] How a virtual machine works.
- [x] Their choice of operating system.
- [x] The basic differences between CentOS and Debian.
- [x] The purpose of virtual machines.
- [x] The difference between aptitude and apt, and what APPArmor is.

## Simple setup
- [x] A password (encryption key) will be requested before attempting to connect to this machine.
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/def2.png\?raw\=true">

- [x] Ensure that the machine does not have a graphical environment at launch.
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/def3.png\?raw\=true">

- [x] Login with a user. This user must **not** be root.
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/def4.png\?raw\=true">

- [x] Check that the UFW service is started with the help of the evaluator.

```console
sudo ufw status
```
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/def5.png\?raw\=true">

- [x] Check that the SSH service is started with the help of the evaluator.
```console
sudo systemctl status sshd
```
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/def6.png\?raw\=true">

- [x] Check that the chosen operating system is Debian or CentOS with the help of the evaluator.
```console
sudo uname -a
```
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/def7.png\?raw\=true">

## User
- [x] Check that the user has been added and that it belongs to the "sudo" and "user42" groups.
```console
groups isojo-go
```
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/def8.png\?raw\=true">

- [x] Create a new user & assign it a password of your choice, respecting the subject rules.
```console
sudo useradd **testuser**
```
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/def9.png\?raw\=true">

- [x] Check the locations of the password rules.

**TBD**


- [x] Create a group named "evaluating".
```console
sudo groupadd **testgroup**
```
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/def10.png\?raw\=true">

- [x] Add the new user to the "evaluating" group.
```console
sudo usermod -aG testgroup testuser
```
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/def11.png\?raw\=true">

- [x] Ask the student being evaluated to explain the advantages of this password policy, as well as the advantages and disadvantages of its implementation.
- [x] Check that the hostname of the machine is correctly formatted as follows: login42 (login of the student being evaluated).
```console
hostname
```
- [x] Modify this hostname by replacing the login with yours, then restart the machine.
```console
sudo hostnamectl set-hostname testuser
```
- [x] Compare partitions for the virtual machine. Note: if thestudent evaluated makes the bonuses, it will be necessary to refer to the bonus example.
- [ ] ```console
lsblk
```
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/def12.png\?raw\=true">

- [x] Ask for explanation of how LVM works and what it is all about.

## SUDO
- [x] Check that the "sudo" program is properly installed on the virtual machine.
- [ ] ```console
dpkg -s sudo
```
- [x] The student being evaluated should now show assigning your new user to the "sudo" group.
```console
sudo usermod -aG sudo testuser
```
- [x] Ask for explanation on the value and operation of sudo using examples of their choice.
- [x] Show the implementation of the rules imposed by the subject.
- [x] Verify that the "/var/log/sudo/" folder exists and has at least one file. 
```console
sudo ls -lap /var/log/sudo
```
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/def13.png\?raw\=true">

- [x] Check the contents of the files in this folder, You should see a history of the commands used with sudo.
```console
sudo nano /var/log/sudo/sudo.log
```
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/def14.png\?raw\=true">

## UFW
- [x] Check that the "UFW" program is properly installed on the virtual machine.
- [x] Check that it is working properly.
- [x] Ask what UFW is and the value of using it.
- [x] List the active rules in UFW. A rule must exist for port 4242.
```console
sudo ufw status
```
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/def15.png\?raw\=true">

- [x] Add a new rule to open port 8080. Check that this one has been added by listing the active rules.
```console
sudo ufw allow 8080
sudo ufw status
```
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/def16.png\?raw\=true">

- [x] Delete this new rule with the help of the student being evaluated.
```console
sudo ufw status numbered
sudo ufw delete 4
```
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/def17.png\?raw\=true">

## SSH
- [x] Check that the SSH service is properly installed on the virtual machine.
- [x] Check that it is working properly.
- [x] Ask what SSH is and the value of using it.
- [x] Ask what Verify that the SSH service only uses port 4242.
- [x] Use SSH in order to log in with the newly created user.
- [x] Make sure that you cannot use SSH with the "root" user as stated in the subject.

## Script monitoring
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/def18.png\?raw\=true">
- [x] How their script works by showing you the code.
- [x] What "cron" is and how set up the script so that it runs every 10 minutes.
- [x] Once the correct functioning of the script has been verified, the student being evaluated should ensure that this script runs **every minute**.
- [x] Stop running the script without modifying it, restart, check that the script, still exists in the same place, that its rights have remained unchanged, and that it has not been modified.

"Stop a cron job
You can stop a single cron job by removing its line from the crontab file. To do that, run the crontab -e command and then delete the line for the specific task. Alternatively, you can stop the cron job by commenting it out in the crontab file."

# Bonus
- [x] Setting up partitions is worth 2 points.
- [x] Setting up WordPress, only with the services required by the subject, is worth 2 points.
- [x] The free choice service is worth 1 point.
