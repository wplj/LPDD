# LPDD
Linux + Powershell + DSC + Docker HowTo

Add Microsoft software repository configuration - https://docs.microsoft.com/en-us/windows-server/administration/Linux-Package-Repository-for-Microsoft-Software
1.	Install PowerShell for Linux - https://docs.microsoft.com/en-us/powershell/scripting/install/installing-powershell-core-on-linux
2.	Install PowerShell DSC for Linux - https://github.com/Microsoft/PowerShell-DSC-for-Linux
	a)	Install Open Management Infrastructure (OMI) server component – https://github.com/Microsoft/omi
	b)	Install DSC package – https://github.com/Microsoft/PowerShell-DSC-for-Linux/releases/latest
3.	Enable OMI server to run on boot –
$ sudo systemctl enable omid.service
Check listening ports and configuration –
/opt/omi/etc/omiserver.conf
4.	Install OMI server certificate (omi.pem) on a managing host (Windows or Linux) as trusted
5.	Add a new user with root rights –
	$ sudo useradd -ou 0 -g 0 admin
	$ sudo passwd admin
	$ sudo usermod -a -G root admin
6.	Install nx PowerShell module, containing standard Linux resources (also on a managing host – Windows or Linux) - https://www.powershellgallery.com/packages/nx
7.	Install Docker, configure Docker group - https://docs.docker.com/install/linux/linux-postinstall if you need
8.	Install Git
9.	Install Visual Studio Code and extensions – PowerShell, Docker, Code Runner + whatever you like
10.	(optional) Install .Net Core SDK https://www.microsoft.com/net/download/linux-package-manager/rhel/sdk-current (for Docker.DotNet)
a)	Install mono
sudo apt-get install mono-complete

DSC with Linux - https://docs.microsoft.com/en-us/powershell/scripting/dsc/getting-started/lnxGettingStarted
PowerShell module for managing Docker with DSC - https://github.com/walked/cDscDocker
Useful links:
 - xDSCResourceDesigner project https://github.com/PowerShell/xDSCResourceDesigner
