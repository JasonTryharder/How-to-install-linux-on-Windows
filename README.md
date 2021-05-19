# How-to-install-linux-on-Windows
describe how to install linux on windows machine
Machine configure : Dell M15R3 Win10 Home
Target to insatll Linux 20.04 LTS
Step1 : Back up your windows to create a recovery drive, follow this link (https://support.microsoft.com/en-us/windows/create-a-recovery-drive-abb4691b-5324-6d4a-8766-73fab304c246) and this link (https://www.easeus.com/backup-recovery/create-a-windows-10-recovery-drive-for-another-computer.html#part1)
Step2 : Download a distribution of Ubuntu (https://ubuntu.com/download/desktop) , Which Ubuntu to use (steps may not be suitable for other version), If in doubt, use the LTS  
Step3 : Check HardDisk Partition Style (http://myviewsonfoss.blogspot.com/2018/05/this-article-willshow-you-how-you-can.html) 
open disk management, or type diskmgmt.msc in comamnd window  ![image](https://user-images.githubusercontent.com/54369499/118752315-d8319080-b830-11eb-8f77-6834c05676b0.png)
Go to Volume Tab, if it shows GUID Partition Table, then your disk partition style is GPT![GPT-Partition](https://user-images.githubusercontent.com/54369499/118752694-9523ed00-b831-11eb-91e9-11af716415c5.png)
If it shows Master Boot Recorder then your Hard Disk partion style is MBR.![MBR-Partition](https://user-images.githubusercontent.com/54369499/118752712-9d7c2800-b831-11eb-8315-826b60ee13a2.png)
Check if UEFI or BIOS , Press Win + R and type msinfo32 and then hit enter and look for BIOS Mode entry in the system information window
this information will be important for later ubuntu installation
![UEFI](https://user-images.githubusercontent.com/54369499/118753311-b6390d80-b832-11eb-9ae9-5d51517ac9cd.png)

Create a bootable USB , follow this, and remeber the partition style, when perform this step in Rufus ![Rufus_Partition_Style_Selection](https://user-images.githubusercontent.com/54369499/118752908-ecc25880-b831-11eb-8d69-dbe54747a216.png)

Create some free space for Ubuntu, by release some space from your disk, warning: do not install Ubuntu on Windows C directly, this will erase your windows, and leave the free space Unallocated 
![image](https://user-images.githubusercontent.com/54369499/118753596-52631480-b833-11eb-9d6d-54fc6c01a5ab.png)

Installation process : 
restart the computer, and press F12 repeatedly and rapidly on opening ( boot operation, choose to boot from USB ) 

Select Ubuntu or install Ubuntu to begin process 
If machine is UEFI and you decide to Dual Boot, you should use Install ubuntu alongside Windows Boot Manager option, click install now, Ubuntu will begin installation and enjoy! 
![image](https://user-images.githubusercontent.com/54369499/118754123-5fccce80-b834-11eb-82a5-14d9ffd0955c.png)

If machine is BIOS (old machine) and you know what you are doing, choose something else 
in this step we need to create partitions for the below information: 
/ (root) – 10 GB
SWAP – 4GB
/home – Remaining (~ 6GB)
![image](https://user-images.githubusercontent.com/54369499/118754466-1f218500-b835-11eb-8f1a-ac7154ab1048.png)

Select the free space and then click on the + sign.

/ (root):

![image](https://user-images.githubusercontent.com/54369499/118754487-2ea0ce00-b835-11eb-8cc9-fc02b8376dcd.png)

Swap:
![image](https://user-images.githubusercontent.com/54369499/118754504-38c2cc80-b835-11eb-90dc-032133e4522f.png)

/home:
![image](https://user-images.githubusercontent.com/54369499/118754521-424c3480-b835-11eb-8bf7-48ec537e1d12.png)

Once you have created partitions, click Install now to write the changes to disk and start the installation.
![image](https://user-images.githubusercontent.com/54369499/118754543-4c6e3300-b835-11eb-9dcc-e211d629e95b.png)

Click Continue to write the changes to disks.
![image](https://user-images.githubusercontent.com/54369499/118754566-5859f500-b835-11eb-938d-2f5a33a1fa93.png)

Boot to Ubuntu or Windows 
![image](https://user-images.githubusercontent.com/54369499/118754680-8ccdb100-b835-11eb-8792-3f8f8cefc455.png)
![image](https://user-images.githubusercontent.com/54369499/118754695-922afb80-b835-11eb-9351-ebabc9bbe2e8.png)

Missing GRUB menu : 
Menu will appear if you press and hold Shift during loading Grub, if you boot using BIOS. When your system boots using UEFI, press Esc.

For permanent change you'll need to edit your /etc/default/grub file -- place a "#" symbol at the start of line GRUB_HIDDEN_TIMEOUT=0.

Save changes and run sudo update-grub to apply changes.

Work arround to turn off intel RST system : link(https://askubuntu.com/questions/1233623/workaround-to-install-ubuntu-20-04-with-intel-rst-systems)
Ubuntu installer won't recognize your HDD/SSD until you switch your disk setting in the BIOS from RAID to AHCI.

Right-click the Windows Start Menu. Choose Command Prompt (Admin).
If you don’t see Command Prompt listed, it’s because you have already been updated to a later version of Windows.  If so, use this method instead to get to the Command Prompt:
Click the Start Button and type cmd
Right-click the result and select Run as administrator
Type this command and press ENTER: bcdedit /set {current} safeboot minimal
If this command does not work for you, try bcdedit /set safeboot minimal
Restart the computer and enter BIOS Setup (the key to press varies between systems).
Change the SATA Operation mode to AHCI from either IDE or RAID (again, the language varies).
Save changes and exit Setup and Windows will automatically boot to Safe Mode.
Right-click the Windows Start Menu once more. Choose Command Prompt (Admin).
Type this command and press ENTER: bcdedit /deletevalue {current} safeboot
If you had to try the alternate command above, you will likely need to do so here also: bcdedit /deletevalue safeboot
Reboot once more and Windows will automatically start with AHCI drivers enabled.

this tutoria not working for me link(https://help.ubuntu.com/rst/)
























