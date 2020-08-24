# CICD_Pipeline_Using_Jenkins

Downmolad thr VM's DISK - https://drive.google.com/drive/folders/1sNSNqU_HF_InCTHg2dg6dG00b7kM0EaU?usp=sharing 
---------------------------------------------------------------------------------------------------------------
Importing an Existing Virtual Machine into VirtualBox
If you use another virtualization platform and have an export of an existing virtual machine in Open Virtualization Format (OVF or OVA), you can import the virtual machine into VirtualBox and use this to prepare the desktop template. To import a virtual machine, you need to start VirtualBox. On the host where you installed Oracle VDI and VirtualBox, on the desktop select the Applications menu, then the System Tools menu, and then Oracle VM VirtualBox. Alternatively, you can run the VirtualBox command in a terminal. The Oracle VM VirtualBox Manager is displayed, as shown in Figure 6.1. 
Figure 6.1. Oracle VM VirtualBox Manager
 

In the File menu, select Import Appliance. The Appliance Import wizard is displayed in a new window, as shown in Figure 6.2 
Figure 6.2. Appliance Import Wizard
 

Click Choose, browse to the location containing the *.ovf or *.ova file of the virtual machine you want to import, and click Open. The Appliance Import Settings step is displayed as shown in Figure 6.3 
Figure 6.3. Appliance Import Settings
 

Make any adjustments you want to the displayed settings (you can also change the settings later) and click Import. The Appliance Import Wizard is closed and after a few moments, the imported virtual machine is listed in Oracle VM VirtualBox Manager. 
After the import, select the imported virtual machine and in the toolbar click the Settings button. Review the virtual machine settings to make sure that the virtual machine has the hardware it needs to operate. Make sure that the virtual machine has a CD/DVD drive. 
Once you have reviewed the settings, select the imported virtual machine and in the toolbar click the Start button. Verify that the virtual machine works. 
 
Import virtual machines
Import a Virtual Machine
Importing a virtual machine registers the virtual machine with the Hyper-V host. You can import back into the host, or new host. If you're importing to the same host, you don't need to export the virtual machine first, because Hyper-V tries to recreate the virtual machine from available files. Importing a virtual machine registers it so it can be used on the Hyper-V host.
The Import Virtual Machine wizard also helps you fix incompatibilities that can exist when moving from one host to another. This is commonly differences in physical hardware, such as memory, virtual switches, and virtual processors.
Import using Hyper-V Manager
To import a virtual machine:
1.	From the Actions menu in Hyper-V Manager, click Import Virtual Machine.
2.	Click Next.
3.	Select the folder that contains the exported files, and click Next.
4.	Select the virtual machine to import.
5.	Choose the import type, and click Next. (For descriptions, see Import types, below.)
6.	Click Finish.
Import using PowerShell
Use the Import-VM cmdlet, following the example for the type of import you want. For descriptions of the types, see Import types, below.
Register in place
This type of import uses the files where they are stored at the time of import and retains the virtual machine's ID. The following command shows an example of an import file. Run a similar command with your own values.
PowerShell
Import-VM -Path 'C:\<vm export path>\2B91FEB3-F1E0-4FFF-B8BE-29CED892A95A.vmcx'
 
Importing Libvirt KVM VMs to oVirt

Importing a VM
Importing a VM is achieved by using the VM’s unique Libvirt name that can be identified via:
$ virsh -r -c 'qemu+tcp://username@host1.example.org/system' list --all
As an example, follow these steps to import a VM named rhel1_local from qemu+tcp://username@host1.example.org/system:
•	Login to the Administration Portal and navigate to the Virtual Machines tab
•	From the toolbar, press the Import button  
•	From the Source box, select KVM (via libvirt) option  
•	Enter qemu+tcp://username@host1.example.org/system in the URI box
•	If authentication is required, check the Requires Authentication checkbox, and enter username/password
•	Press the Load button  
•	In the box labeled Virtual Machines on Source, you should see all the VMs that are in ‘Down status’
•	Select the VM rhel1_local and click the right arrow -> to move it to the Virtual Machines to Import box
  
•	Click, Next
  
•	In this dialog you can adjust the VM properties such as operating system and allocation policy
•	Press the OK button  
•	You should see the rhel1_local VM listed in the Virtual Machines tab, and the import process should start shortly
