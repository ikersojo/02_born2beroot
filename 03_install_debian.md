# Install Debian
## Basic localization and user definition
- The machine will boot from the .iso disk 
- Select **Install** to start the Debian installation process.
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img1.png\?raw\=true">

- Choose language: **English**.
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img2.png\?raw\=true">

- Choose localization:  **other/Europe/Spain**.
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img3.png\?raw\=true">
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img4.png\?raw\=true">
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img5.png\?raw\=true">

- Choose locale: **en_US.UTF-8**
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img6.png\?raw\=true">

- Choose Keyboard layout: **Spanish**.
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img7.png\?raw\=true">

- Select hostname: **isojo-go42**.
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img8.png\?raw\=true">

- Leave the domain name **blank**.
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img9.png\?raw\=true">

- Introduce the root password. **Write down this password for the evaluation!**
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img10.png\?raw\=true">
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img11.png\?raw\=true">

- Create the first user, which is the **isojo-go**: first **full name**, then **username** and then **password**. **Write everything down for evaluation!**
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img12.png\?raw\=true">
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img13.png\?raw\=true">
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img14.png\?raw\=true">
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img15.png\?raw\=true">

- Select clock: **Madrid**
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img16.png\?raw\=true">

## Partitions, LVM and Encryption
For further background on the Linux Filesystem and why the partitioning, see [partitions_info](https://github.com/ikersojo/02_born2beroot/blob/main/extra/partitions_info.md).

The **bonus partition table** will be followed.
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/bonus_partition_table.png\?raw\=true">

- Select **Manual**
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img17.png\?raw\=true">

- Choose the hard disk (sda) 
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img18.png\?raw\=true">

- Create **new** partition table
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img19.png\?raw\=true">

- Choose **free space**
	- Create new partition
		- Define Size (500MB)
			- Partition type: **Primary**
				- Locate the partition at the **beginning** of the drive
					- Mount point: **/boot**
					- Bootable flag: **on** (this is not mandatory)
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img20.png\?raw\=true">
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img21.png\?raw\=true">
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img22.png\?raw\=true">
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img23.png\?raw\=true">
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img24.png\?raw\=true">
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img25.png\?raw\=true">

- Choose **free space**
	- Create new partition
		- Define Size (max)
			- Partition type: logic
				- Mount point: DO NOT MOUNT
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img26.png\?raw\=true">
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img27.png\?raw\=true">
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img28.png\?raw\=true">

- Select **Configure Encrypted Volumes**
	- Save changes: YES
		- Select sda5 (using space bar to actually “select” the partition)
			- Select **Finish** / Select **Done** / Wait for the encryption to take place
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img29.png\?raw\=true">
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img30.png\?raw\=true">
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img31.png\?raw\=true">
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img32.png\?raw\=true">
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img33.png\?raw\=true">
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img34.png\?raw\=true">
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img35.png\?raw\=true">

- Enter encryption password (twice)
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img36.png\?raw\=true">
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img37.png\?raw\=true">

- Select **Configure LVM**
	- Save changes: **YES**
		- Create **volume group**
			- Introduce group name: **LVMGroup**
				- Select /dev/mapper/sda5_crypt
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img38.png\?raw\=true">
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img39.png\?raw\=true">
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img40.png\?raw\=true">
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img41.png\?raw\=true">
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img42.png\?raw\=true">

- Create logic volume
**sda5_crypt 30G:**
	- root: 10G
	- swap: 2.3G
	- home: 5G
	- var: 3G
	- srv: 3G
	- tmp: 3G
	- var-log: 4G
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img43.png\?raw\=true">
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img44.png\?raw\=true">
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img45.png\?raw\=true">
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img46.png\?raw\=true">
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img47.png\?raw\=true">

- Check volumes
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img48.png\?raw\=true">
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img49.png\?raw\=true">
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img50.png\?raw\=true">

- Configure Volumes (each /xxxx):
	- Ext4 journaling file system (except for SWAP)
	- Mount point: /xxxx
	- Finish partition
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img52.png\?raw\=true">
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img51.png\?raw\=true">
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img53.png\?raw\=true">

- Finish partitioning
	- Write changes to disk (overwrite)
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img54.png\?raw\=true">

## Complete Debian installation
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img55.png\?raw\=true">

- Select country: **Spain**
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img56.png\?raw\=true">

- Select mirror: **deb.debian.org**
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img57.png\?raw\=true">

- Left **blank** HTTP proxy
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img58.png\?raw\=true">

- Select **not** to take part on survey
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img59.png\?raw\=true">

- Software selection: **Uncheck all items** (using space bar)
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img60.png\?raw\=true">

- Agree to **install grub** in sda
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img61.png\?raw\=true">
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img62.png\?raw\=true">

- Finish and reboot
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img63.png\?raw\=true">

## Update the system
- Introduce encryption password
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img64.png\?raw\=true">

- Login as “root”
<img  width="800" src="https://github.com/ikersojo/02_born2beroot/blob/main/img/born2beroot_img65.png\?raw\=true">

- Update package list and Upgrade system
```console
apt update
apt upgrade
```
- Reboot
```console
reboot
```