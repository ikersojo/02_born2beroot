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
# OS architecture and kernel version:
ARCH=$(uname -srvmo)

# Number of physical processors:
PCPU=$(grep 'physical id' /proc/cpuinfo | uniq | wc -l)

# Number of virtual processors:
VCPU=$(grep processor /proc/cpuinfo | uniq | wc -l)

# Current available RAM on the server and its utilization rate as a percentage:
RAM_TOTAL=$(free -h | grep Mem | awk '{print $2}')
RAM_USED=$(free -h | grep Mem | awk '{print $3}')
RAM_PERC=$(free -k | grep Mem | awk '{printf("%.2f%%"), $3 / $2 * 100}')

# Current available disc space on the server and its utilization rate as a percentage:
DISK_TOTAL=$(df -h --total | grep total | awk '{print $2}')
DISK_USED=$(df -h --total | grep total | awk '{print $3}')
DISK_PERC=$(df -k --total | grep total | awk '{print $5}')

# Current utilization rate of the processors as a percentage:
CPU_LOAD=$(top -bn1 | grep '^%Cpu' | xargs | awk '{printf("%.1f%%"), $2 + $4}')

# Last boot:
LAST_BOOT=$(who -b | awk '{print($3 " " $4)}')
# alt: $(who -b | awk G')

# Whether LVM is active or not:
LVM=$(if [ $(lsblk | grep lvm | wc -l) -eq 0 ]; then echo no; else echo yes; fi)

# Number of active connections:
TCP=$(grep TCP /proc/net/sockstat | awk '{print $3}')

# Number of users using the server:
USER_LOG=$(who | wc -l)

# IP and MAC address:
IP_ADDR=$(hostname -I | awk '{print $1}')
MAC_ADDR=$(ip link show | grep link/ether | awk '{print $2}')

# Number of commands executed with the sudo program:
SUDO_LOG=$(cat /var/log/sudo/sudo.log | grep USER | wc -l)

# Print to Screen:
echo "-----------------------------------------------------------"
echo "  # Architecture    : "$ARCH
echo "  # Physical CPUs   : "$PCPU
echo "  # Virtual CPUs    : "$VCPU
echo "  # Memory Usage    : "$RAM_USED"/"$RAM_TOTAL" ("$RAM_PERC")"
echo "  # Disk Usage      : "$DISK_USED"/"$DISK_TOTAL" ("$DISK_PERC")"
echo "  # CPU Load        : "$CPU_LOAD
echo "  # Last Boot       : "$LAST_BOOT
echo "  # LVM use         : "$LVM
echo "  # TCP Connections : "$TCP" established"
echo "  # Users logged    : "$USER_LOG
echo "  # Network         : IP "$IP_ADDR" (MAC "$MAC_ADDR")"
echo "  # Sudo            : "$SUDO_LOG" commands used"
echo "-----------------------------------------------------------"

```

## Cron
### What is Cron?
Cron is a utility in a Linux or UNIX-like operating system that allows running commands or scripts on a given schedule without any user intervention. The scheduled commands and scripts are also named as cron jobs. It is mostly used for automating recurring jobs like running scheduled backups, cleaning temporary files, system maintenance, and various other recurring jobs. 

Login as root to be able to place the script in as root user.

It is installed by default in Debian,but need to be enabled:
```console
systemctl enable cron
```

Cron uses crontab files to schedule jobs. Each user can have one, or many. As the root user, we will now create one with the following command:
```console
crontab -e
```

The following syntax is used:
```console
.------------------------ minutes (0-59) - exact minute (if we add "/" symbol, it means "every")
| .-------------------- hours (0-23)
| | .---------------- day of the month (1-31)
| | | .------------ month of the year (1-12)
| | | | .-------- day of the week (0-6, 0 = sunday)
| | | | |
* * * * * <command to execute>
```

Therfore:
```console
*/10 * * * * bash /root/monitoring.sh | wall
```

<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/cron.png\?raw\=true">

wall is added to print in all terminal sessions.
