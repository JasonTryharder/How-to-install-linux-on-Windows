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







