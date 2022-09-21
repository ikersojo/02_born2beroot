# Born2beroot - Virtual Machine creation
## Introduction
This project aims to introduce you to the wonderful world of virtualization. You will create your first machine in VirtualBox (or UTM if you can’t use VirtualBox) under specific instructions. Then, at the end of this project, you will be able to set up your own operating system while implementing strict rules. You only have to turn in a signature.txt file at the root of your repository. You must paste in it the signature of your machine’s virtual disk. Go to Submission and peer-evaluation for more information
### What is a Virtual Machine?
A Virtual Machine (VM) is a compute resource that uses software instead of a physical computer to run programs and deploy apps. One or more virtual “guest” machines run on a physical “host” machine.  Each virtual machine runs its own operating system and functions separately from the other VMs, even when they are all running on the same host. This means that, for example, a virtual MacOS virtual machine can run on a physical PC. 

Virtual machine technology is used for many use cases across on-premises and cloud environments. More recently, public cloud services are using virtual machines to provide virtual application resources to multiple users at once, for even more cost efficient and flexible compute.
### What are virtual machines used for?
Virtual machines (VMs) allow a business to run an operating system that behaves like a completely separate computer in an app window on a desktop. VMs may be deployed to accommodate different levels of processing power needs, to run software that requires a different operating system, or to test applications in a safe, sandboxed environment.
Virtual machines have historically been used for server virtualization, which enables IT teams to consolidate their computing resources and improve efficiency. Additionally, virtual machines can perform specific tasks considered too risky to carry out in a host environment, such as accessing virus-infected data or testing operating systems. Since the virtual machine is separated from the rest of the system, the software inside the virtual machine cannot tamper with the host computer.  
### How do virtual machines work?
The virtual machine runs as a process in an application window, similar to any other application, on the operating system of the physical machine. Key files that make up a virtual machine include a log file, NVRAM setting file, virtual disk file and configuration file. 
### Advantages of virtual machines
- Virtual machines are easy to manage and maintain, and they offer several advantages over physical machines:   
- VMs can run multiple operating system environments on a single physical computer, saving physical space, time and management costs. 
- Virtual machines support legacy applications, reducing the cost of migrating to a new operating system. For example, a Linux virtual machine running a distribution of Linux as the guest operating system can exist on a host server that is running a non-Linux operating system, such as Windows. 
- VMs can also provide integrated disaster recovery and application provisioning options. 
### Disadvantages of virtual machines
- While virtual machines have several advantages over physical machines, there are also some potential disadvantages: 
- Running multiple virtual machines on one physical machine can result in unstable performance if infrastructure requirements are not met. 
- Virtual machines are less efficient and run slower than a full physical computer. Most enterprises use a combination of physical and virtual infrastructure to balance the corresponding advantages and disadvantages. 
### The two types of virtual machines
Users can choose from two different types of virtual machines—process VMs and system VMs:  
- A process virtual machine allows a single process to run as an application on a host machine, providing a platform-independent programming environment by masking the information of the underlying hardware or operating system. An example of a process VM is the Java Virtual Machine, which enables any operating system to run Java applications as if they were native to that system.   
- A system virtual machine is fully virtualized to substitute for a physical machine. A system platform supports the sharing of a host computer’s physical resources between multiple virtual machines, each running its own copy of the operating system. This virtualization process relies on a hypervisor, which can run on bare hardware, such as VMware ESXi, or on top of an operating system.  
### What are 5 types of virtualization?
All the components of a traditional data center or IT infrastructure can be virtualized today, with various specific types of virtualization:   
- Hardware virtualization: When virtualizing hardware, virtual versions of computers and operating systems (VMs) are created and consolidated into a single, primary, physical server. A hypervisor communicates directly with a physical server’s disk space and CPU to manage the VMs. Hardware virtualization, which is also known as server virtualization, allows hardware resources to be utilized more efficiently and for one machine to simultaneously run different operating systems. 
- Software virtualization: Software virtualization creates a computer system complete with hardware that allows one or more guest operating systems to run on a physical host machine. For example, Android OS can run on a host machine that is natively using a Microsoft Windows OS, utilizing the same hardware as the host machine does. Additionally, applications can be virtualized and delivered from a server to an end user’s device, such as a laptop or smartphone. This allows employees to access centrally hosted applications when working remotely. 
- Storage virtualization: Storage can be virtualized by consolidating multiple physical storage devices to appear as a single storage device. Benefits include increased performance and speed, load balancing and reduced costs. Storage virtualization also helps with disaster recovery planning, as virtual storage data can be duplicated and quickly transferred to another location, reducing downtime.  
- Network virtualization: Multiple sub-networks can be created on the same physical network by combining equipment into a single, software-based virtual network resource. Network virtualization also divides available bandwidth into multiple, independent channels, each of which can be assigned to servers and devices in real time. Advantages include increased reliability, network speed, security and better monitoring of data usage. Network virtualization can be a good choice for companies with a high volume of users who need access at all times. 
- Desktop virtualization: This common type of virtualization separates the desktop environment from the physical device and stores a desktop on a remote server, allowing users to access their desktops from anywhere on any device. In addition to easy accessibility, benefits of virtual desktops include better data security, cost savings on software licenses and updates, and ease of management. 
### Container vs virtual machine
Like virtual machines, container technology such as Kubernetes is similar in the sense of running isolated applications on a single platform. While virtual machines virtualize the hardware layer to create a “computer,” containers package up just a single app along with its dependencies. Virtual machines are often managed by a hypervisor, whereas container systems provide shared operating system services from the underlying host and isolate the applications using virtual-memory hardware.  
A key benefit of containers is that they have less overhead compared to virtual machines. Containers include only the binaries, libraries and other required dependencies, and the application. Containers that are on the same host share the same operating system kernel, making containers much smaller than virtual machines. As a result, containers boot faster, maximize server resources, and make delivering applications easier. Containers have become popluar for use cases such as web applications, DevOps testing, microservices and maximizing the number of apps that can be deployed per server.  
Virtual machines are larger and slower to boot than containers. They are logically isolated from one another, with their own operating system kernel, and offer the benefits of a completely separate operating system. Virtual machines are best for running multiple applications together, monolithic applications, isolation between apps, and for legacy apps running on older operating systems. Containers and virtual machines may also be used together. his means that, for example, a virtual MacOS virtual machine can run on a physical PC. 
## CentOS vs Debian
### Debian
Debian, also known as Debian GNU/Linux, is a Linux distribution composed of free and open-source software, developed by the community-supported Debian Project, which was established by Ian Murdock on August 16, 1993. The first version of Debian (0.01) was released on September 15, 1993, and its first stable version (1.1) was released on June 17, 1996. The Debian Stable branch is the most popular edition for personal computers and servers. Debian is also the basis for many other distributions, most notably Ubuntu.
Debian is one of the oldest operating systems based on the Linux kernel. The project is coordinated over the Internet by a team of volunteers guided by the Debian Project Leader and three foundational documents: the Debian Social Contract, the Debian Constitution, and the Debian Free Software Guidelines. New distributions are updated continually, and the next candidate is released after a time-based freeze.
Since its founding, Debian has been developed openly and distributed freely according to the principles of the GNU Project. Because of this, the Free Software Foundation sponsored the project from November 1994 to November 1995. When the sponsorship ended, the Debian Project formed the nonprofit organization Software in the Public Interest to continue financially supporting development.
### CentOS
CentOS (from Community Enterprise Operating System; also known as CentOS Linux) is a Linux distribution that provides a free and open-source community-supported computing platform, functionally compatible with its upstream source, Red Hat Enterprise Linux (RHEL). In January 2014, CentOS announced the official joining with Red Hat while staying independent from RHEL.
The first CentOS release in May 2004, numbered as CentOS version 2, was forked from RHEL version 2.1AS. Since version 8, CentOS officially supports the x86-64, ARM64, and POWER8 architectures, and releases up to version 6 also supported the IA-32 architecture. As of December 2015, AltArch releases of CentOS 7 are available for the IA-32 architecture, Power ISA, and for the ARMv7hl and AArch64 variants of the ARM architecture. CentOS 8 was released on 24 September 2019.

In December 2020, Red Hat unilaterally terminated CentOS development. In response, CentOS founder Gregory Kurtzer created the Rocky Linux project as a successor to the original mission of CentOS. In March 2021, Cloud Linux (makers of CloudLinux OS) released a new RHEL derivative called AlmaLinux.
While the distribution was discontinued at the end of 2021, development of CentOS Stream, its midstream variant, continues.
### Which OS to choose for Born2beroot?
I will be selecting Debian, because is more widely used and is still on development. It is also recommended by the subject.

The Debian iso image : https://cdimage.debian.org/debian-cd/current/amd64/iso-cd/debian-11.5.0-amd64-netinst.iso

## Preparing goinfre directory (only for 42 school computers)
This is required to be able to house the VM itself, due to size limitations of the regular user folder.
- Create folder in /sgoinfre/goinfre/Perso/**username** with the user name:
```console
mkdir sgoinfre/goinfre/Perso/isojo-go
```
- Check folder permissions (they should be drwxr-xr-x): 
```console
sgoinfre/goinfre/Perso/
ls -lap
```
- Change permissions to drwx------:
```console
chmod 700 isojo-go
```
- We can also create a direct link to the folder using the command:
```console
ln -s /sgoinfre/goinfre/Perso/isojo-go ~/goinfre
```
 
## Creating the Virtual Machine
VirtualBox will be used to create the virtual machine. Click NEW to start defining a New Virtual Machine.
### Name and location
- Name: born2beroot
 - Machine Folder: /sgoinfre/goinfre/Perso/isojo-go
- Type: Linux
- Version: Debian (64-bit)
### Memory allocation
- 1 GB is fine
### Hard Disk
- Create a Virtual hard disk
- VDI type (Virtual Disk Image)
- Dynamic Allocation
- Confirm the location of the .vdi file
- Allocate hard disk space:
- 30GB as requested by the subject
- Allocate 16GB of hard disk space (recommended by peers at 42 school); the subject asks for 30GB allocation but is not required (even for the bonus part) and will make the signature creation a very lengthy step.
### Installation media
- Select the virtual machine and go to storage
- Select the debian installation media (.iso file)
### Network adapter
- Attached to: Bridge Adapter
- Name: en0: Ethernat

 
## Install Debian
### Basic localization and user definition
- The machine will boot from the .iso disk 
- Select **Install** to start the Debian installation process.
- Choose language: **English**.
- Choose localization:  **other/Europe/Spain**.
- Choose Keyboard layout: **Spanish (QWERTY)**.
- Select hostname: **isojo-go42**.
- Leave the domain name **blank**.
- Introduce the root password. **Write down this password for the evaluation!**
- Create the first user, which is the **isojo-go**: first **full name**, then **username** and then **password**. **Write everything down for evaluation!**
- Select clock

 
### Partitions, LVM and Encryption
#### Why have different partitions?
The aim is to have each type of information / function isolated on a different partition to isolate issues and protect the rest of the system. A good practice can be mount each key part of the linux/unix file system structure in a different partition.
#### File System Structure
The most significant difference between windows and linux/unix file systems is determining where the file system’s root begins. In Windows, the root starts with the drive letter, generally C:, which indicates it starts with the hard disc. However, in Linux, the root of the filesystem does not correlate to a physical device or location; rather, it is a logical position of just “/”, which can be located in any hard disk. Any other directory can also be located (mounted) in a different hard disk, but as a user navigating the file system tree, the physical location of the directory is transparent.
 
Another thing to remember is that everything in Linux is a file. Alternatively, everything is shown as a file, whereas in Windows it may be displayed as a hard drive. In Windows, for example, the hard drive is commonly represented as C: in the file explorer, and it will even display a small symbol of the hard drive and the amount of space that is being used. In Linux, however, the hard disc is simply represented as /dev/sda, which is really just a directory, which in Linux is really just a file that points to other files.
- / – this is known as “root”, the logical beginning of the Linux file system structure. Every single file path in Linux begins from root. It contains the entirety of your operating system. A key thing to note is that even when any of the /xxx directories below are stored on different partition, it is still logically located at /xxx as far as Linux is concerned.
- /boot – this is where all the needed files for Linux to boot are kept. 
- /home –personal data. The /home/username directory contains the Desktop, Documents, Downloads, Photos, Videos… folders.
- /root – This is the equivalent to the /home folder specifically for the root user, also called the superuser.
- /bin –this is where most of your binary files are stored, typically for the Linux terminal commands and core utilities, such as cd (change directory), pwd (print working directory), mv (move), and so on.
- /sbin – Similar to /bin, except that it’s dedicated to certain commands that can only be run by the root user, or the superuser.
- /lib – this is the location of libraries. When installing Linux software packages, you’ll notice that additional libraries are frequently downloaded, and they almost always begin with lib-something. These are the files required for your Linux apps to function. These libraries can be shared between different programs.
- /opt – Optional software for your system that is not already managed by your distro’s package manager.
- /etc – this is where configuration files are stored. Configurations stored in /etc will typically affect all users on the system; whereas users can also store configuration files under their own /home folders, which will only affect that particular user.
- /dev – this is where physical devices are mounted, such as your hard drives, USB drives, optical drives, and so on. The system hard drive is typically mounted under /dev/sda, whereas your USB thumb drive might be mounted under /dev/sde. You may also have different partitions on your disk, so you’ll see /dev/sda1, /dev/sda2, and so on. In Windows, when you go to “My Computer” or “Computer” and you can see all of the physical devices and drives connected to your computer, this is the equivalent of /dev in Linux file structure.
- /media – Another place where external devices such as optical drives and USB drives can be mounted. This varies between different Linux distros.
- /mnt – This is basically a placeholder folder used for mounting other folders or drives. Typically this is used for Network locations, but you could really use it for anything you want. I used to use it as the mount point for my media server’s hard drive (/mnt/server).
- /proc – the “processes” folder where a lot of system information is represented as files (remember, everything is a file). It basically provides a way for the Linux kernel (the core of the operating system) to send and receive information from various processes running in the Linux environment.
- /tmp – This is where temporary files are stored, and they are usually deleted upon shutdown, which saves you from having to manually delete them.
- /usr – Contains files and utilities that are shared between users.
- /var – This is where variable data is kept, usually system logs but can also include other types of data as well.
- /srv – directory contains site-specific data served by your system running Red Hat Enterprise Linux. This directory gives users the location of data files for a particular service, such as FTP, WWW, or CVS. Data that only pertains to a specific user should go in the /home/ directory.
#### What is LVM ?
The Logical Volume Manager (LVM for short) is a flexible and dynamic management system for Linux hard disk memory. It allows us to have as many partitions as necessary, and to resize, move and even freeze them, without having to restart the machine. This “virtual partitioning” system is very useful on a server, which must preserve stability and rapid management of its memory resources.

With LVM, a physical partition is assigned to a logical volume group and is then “partitioned” into several logical volumes. An additional partition will automatically be created when we define an LVM partition. It is an extended partition which serves only as a container for the logical volumes and doesn’t contain any other data.
#### File Systems
- Ext, Ext2, Ext3 and Ext4 file system: The file system Ext stands for Extended File System. It was primarily developed for MINIX OS. The Ext file system is an older version, and is no longer used due to some limitations. Ext2 is the first Linux file system that allows managing two terabytes of data. Ext3 is developed through Ext2; it is an upgraded version of Ext2 and contains backward compatibility. The major drawback of Ext3 is that it does not support servers because this file system does not support file recovery and disk snapshot. Ext4 file system is the faster file system among all the Ext file systems. It is a very compatible option for the SSD (solid-state drive) disks, and it is the default file system in Linux distribution.
- Btrfs stands for the B tree file system. It is used for fault tolerance, repair system, fun administration, extensive storage configuration, and more. It is not a good suit for the production system.
- The swap file system is used for memory paging in Linux operating system during the system hibernation. A system that never goes in hibernate state is required to have swap space equal to its RAM size.
#### Step by step process
- The bonus partition table will be followed.
 
- Select Manual
- Choose the hard disk (SCSI1) 
- Create new partition table
- Choose free space
	- Create new partition
		- Define Size (500MB)
			- Partition type: Primary
				- Locate the partition at the beginning of the drive
					- Mount point: /boot
- Choose free space
	- Create new partition
		- Define Size (max)
			- Partition type: logic
					- Mount point: DO NOT MOUNT
- Select Configure Encrypted Volumes
	- Save changes: YES
		- Select sda5 (using space bar to actually “select” the partition)
- Select Finish / Select Done / Wait for the encryption to take place
- Enter encryption password (twice)
- Select Configure LVM
	- Save changes: YES
		- Create volume group
			- Introduce group name: LVMGroup
				- Select /dev/mapper/sda5_crypt
					- Create logic volume
- Create volumes:

sda5_crypt		30G

      LVMGroup-root	10G

      LVMGroup-swap	2.3G

      LVMGroup-home	5G

      LVMGroup-var	3G

      LVMGroup-srv	3G

      LVMGroup-tmp	3G

      LVMGroup-var-log	4G	* use var - - log

- Configure Volumes:
	- Ext4 journaling file system (except for SWAP)
	- Mount point: /xxxx
	- Finish partition
- Finish partitioning
	- Write changes to disk (overwrite)

### Complete Debian installation
- Select country: **Spain**
- Select mirror: **deb.debian.org**
- Left **blank** HTTP proxy
- Select **not** to take part on survey
- Software selection: **Uncheck all items** (using space bar)
- Agree to **install grub** in sda
- Finish and reboot

## Update the system
- Introduce encryption password
- Login as “root”
- Update package list and Upgrade system
```console
apt update
apt upgrade
```
- Reboot
```console
	Reboot
```

 
## Configure the Debian System
### Install sudo
The sudo command allows to run programs with the security privileges of another user (by default, as the superuser). It prompts for your user password and confirms the request to execute a command by checking a file, called sudoers, which the system administrator configures.
- Introduce encryption password
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
- Introduce encryption password
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

 
### Install and configure SSH
- Install openssh server:
```console
	sudo apt install openssh-server 
```
- Edit ssh config file:
```console
	sudo nano /etc/ssh/sshd_config
	- “# Port 22”  “Port 4242” (uncomment and change port)
	- “# PermitRootLogin prohibit-password”  “PermitRootLogin no”
- Reboot
```console
	sudo reboot
```
- Check status (focus on port 4242):
```console
	systemctl status ssh
```

### Install and configure UFW firewall
- Install openssh server:
```console
sudo apt install ufw
sudo ufw enable
sudo ufw allow 4242
sudo ufw status
```
- Get and write down ip address:
```console
ip a s
```
### Check SSH concetion
- Go to host mac terminal
```console
ssh isojo-go@ip-address -p 4242
```
- If everything is fine, logout and close:
```console
logout
exit
```

