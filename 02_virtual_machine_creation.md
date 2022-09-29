# Virtual Machine creation
## Preparing goinfre directory
This is required to be able to house the VM itself, due to size limitations of the regular user folder.
- Create folder in /sgoinfre/goinfre/Perso/**username** with the user name:
```console
mkdir sgoinfre/goinfre/Perso/isojo-go
```
- Check folder permissions (they should be drwxr-xr-x): 
```console
cd sgoinfre/goinfre/Perso/
ls -lap
```
- Change permissions to drwx------:
```console
chmod 700 isojo-go
```
- We can also create a direct link to the folder using the command:
```console
ln -s /sgoinfre/goinfre/Perso/isojo-go ~/goinfrePERSO
```
## Creating the Virtual Machine
VirtualBox will be used to create the virtual machine. Click NEW to start defining a New Virtual Machine.
### Name and location
- Name: born2beroot
- Machine Folder: /sgoinfre/goinfre/Perso/isojo-go
- Type: Linux
- Version: Debian (64-bit)
- Snapshot folder also in goingfre user folder.
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
- Remove floppy disc
### Network adapter
- Attached to: Bridge Adapter
- Name: en0: Ethernet