# Monitoring Script
## Script definition
- Create the script in /root folder:
```console
sudo touch /root/monitoring.sh
sudo chmod 755 /root/monitoring.sh
sudo nano /root/monitoring.sh
```

- Include the following script:
```console
#!/bin/bash
echo "#Architecture:" $(uname -a)
echo "#CPU physical:" $(lscpu | awk ' NR==5 {print $2}')
echo "#vCPU :" $(lscpu | grep Socket\(s\) | awk '{print $2}')
free --mega | awk 'NR==2{printf "#Memory Usage: %s/%sMB (%.2f%%)\n", $3,$2,$3*100/$2 }'
df -h | awk '$NF=="/"{printf "#Disk Usage: %d/%dGB (%s)\n", $3,$2,$5}'
top -bn1 | grep load | awk '{printf "#CPU Load: %.2f%s\n", $(NF-2), "%"}'
echo "#Last boot:" $(who -b | awk G')
echo "#LVM use:" $(sudo lvm pvdisplay | grep Allocatable | awk '{print $2}')
echo "#Connetions TCP:" $(ss -s | grep TCP | awk 'NR==2 {printf "%d ESTABLISHED\n", $3}')
echo "#User log:" $(who | wc -l)
echo "#Network: IP" $(hostname -I) $(ip a | grep link/ether | awk '{printf " (%s)\n", $2}')
echo "#Sudo : " $(cat /var/log/sudo/sudo.log | grep USER | wc | awk '{printf "%s cmd\n", $1}')
```

## Cron
### What is Cron?
Cron is a utility in a Linux or UNIX-like operating system that allows running commands or scripts on a given schedule without any user intervention. The scheduled commands and scripts are also named as cron jobs. It is mostly used for automating recurring jobs like running scheduled backups, cleaning temporary files, system maintenance, and various other recurring jobs.
### Configure a Cron job
Open cron tab as root:
```console
sudo crontab -u root -e
```
- Edit the following: | m | h | dom | mon | dow | command|
	- m = minutes
	- h = hours
	- dom = day of month (1 -31)
	- mon = month (1 -12)
	- dow = day of the week (0sunday - 6 saturday)
	- command to be executed

- Use https://crontab.guru to derive the *.
- Use "| wall" to confirm that all terminals display the script.
### Check Cron job
```console
$ sudo crontab -u root -l
```