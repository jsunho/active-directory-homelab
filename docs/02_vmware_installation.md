In this part of my homelab project, I installed VMware Workstation Pro and prepared a virtual machine that will later become my first Windows Server 2022 domain controller.

## 1. Installing VMware Workstation Pro

I downloaded VMware Workstation Pro 25H2 for Windows from the Broadcom website and installed it using the default setup options.
After the installation, I downloaded the Windows Server 2022 ISO, which I will use to install the operating system on the virtual machine.

## 2. Preparing the Virtual Machine

I opened VMware Workstation Pro and created a new virtual machine.
To avoid issues with VMware’s automatic detection, I chose:

  Create a New Virtual Machine → I will install the operating system later

As the operating system type, I selected Windows Server 2022.

  ### VM Specifications
    - 2 vCPUs
    - 4 GB RAM
    - 20 GB virtual disk
    - NAT network mode (good for isolated homelab environments)

After confirming the settings, the VM was created.

### Mounting the ISO

In the VM settings, under CD/DVD (SATA), I selected Use ISO image file and attached the Windows Server 2022 ISO.
Then I powered on the VM.

## 3. Installing Windows Server 2022

During boot, VMware displayed “Press any key to boot from CD or DVD…”, and I pressed a key to start the installation from the ISO.
I selected the language and keyboard layout and proceeded with Install now.

### Windows Edition

I selected:
  
  Windows Server 2022 Standard (Desktop Experience)

because I want the graphical interface.

After accepting the license terms, I chose Custom installation and installed Windows on the virtual disk.
When prompted, I set an Administrator password.
After the installation finished and the server rebooted, I logged into Windows for the first time.

## 4. Preparing the Server

Server Manager opened automatically. I kept the default configuration for now, since the domain controller setup will be done in the next step.

## 5. Installing Active Directory Domain Services (AD DS)

To prepare the server for Active Directory, I opened:
 
 Server Manager → Manage → Add Roles and Features

I used the Role-based installation and selected my local server.
From the roles list, I enabled:
  
  Active Directory Domain Services

The wizard also added the required features, including Group Policy Management.

After confirming the selections, I started the installation.
When it finished, Server Manager displayed a new action:

  Promote this server to a domain controller

This is where the next part of my documentation will continue.