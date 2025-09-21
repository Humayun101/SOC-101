need 2 instances of the operating systems
Linux and Windows

and a Hypervisor to create and manage Virtual machines
- Virtual Box
[Downloads – Oracle VirtualBox](https://www.virtualbox.org/wiki/Downloads)

for instances 
**[Windows 10 Enterprise | Microsoft Evaluation Center](https://www.microsoft.com/en-us/evalcenter/download-windows-10-enterprise?msockid=0759d7977ea36ec018c8c21a7fc36f11)**

once install, set it up on virtual box and install the windows VM 
also install guest addition cd image
make sure to set clipboard to bidirectional from windows to host or vice versa

for the attack defence lab setup, do the following windows configuration
- Disable windows defender (check by Invoke-Mimikatz or EICAR test file)
	- you can choose to use defender control to completely block it
		- [Defender Control v2.1](https://www.sordum.org/9480/defender-control-v2-1/)
- download git to copy resources files, the link is
	- [Git - Downloading Package](https://git-scm.com/downloads/win)
	- link to resource file [GitHub - MalwareCube/SOC101: https://academy.tcm-sec.com/](https://github.com/MalwareCube/SOC101)
	- once git is download, clone the file to ur local drive
	

for ubuntu
[Download Ubuntu Desktop | Ubuntu](https://ubuntu.com/download/desktop)
AFTER INSTALLING
do the following for linux configuration
sudo apt update
sudo apt install bzip2 tar gcc perl make git
sudo apt install linux-headers-generic
sudo apt install linux-headers-$(uname -r){this will confirm that the upper cmd runned succesfullyt and installed}

this will allow to install guest addition cd image
after getting addition image, do the following 

![[Pasted image 20250921202522.png]]
You can now enter full screen and set clipboard to bidirectional from linux to host or vice versa for maximum optimization

To configure Linux, use git clone to get the resource files
humayun@Ubuntu-SOC:~/Documents$ git clone https://github.com/MalwareCube/SOC101.git

**LAB NETWORK CONFIGURATION**
network should be configured as such that both VM should talk to each other but not to host
for that
- Create a network using hypervisor tool
- Create a natnetwork
- once create go to setting of both and do
	- Setting>Network>enable adapter one and choose NAT network we created 
	open both machine and ping ip to each other

By the end of lab setup, u should have
both operating system in VM
Both configured and optimized
both have the resources file in em
both have network configured as above