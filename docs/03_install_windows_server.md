In this part of my homelab project, I promoted my Windows Server 2022 virtual machine to a domain controller. This step completes the basic Active Directory setup and prepares the server for creating users, groups, OUs, and later GPO and DNS configurations.

## 1. Starting the Domain Controller Promotion

After installing the Active Directory Domain Services (AD DS) role in the previous step, Server Manager showed a notification.
I clicked:

  Promote this server to a domain controller

This opened the Active Directory Domain Services Configuration Wizard.

## 2. Creating a New Forest

Since this is a fresh homelab environment, I selected:

  Add a new forest

For the domain name, I chose:

    jsun.local

Using “.local” makes it clear that this domain is only for homelab use and not for public DNS.

## 3. Domain Controller Options

On the next page, I kept the default forest and domain functional levels (Windows Server 2016).
I also left DNS Server enabled, since DNS is required for Active Directory to work.

The wizard asked for a DSRM password (Directory Services Restore Mode).
I set a password and noted it down, because this password is used when repairing or recovering Active Directory.

All other settings stayed at their defaults.

## 4. Additional Configuration

The wizard automatically generated the NetBIOS domain name, which in my case was:

JSUN

For the database, log files, and SYSVOL locations, I kept the default paths:

  C:\Windows\NTDS  
  C:\Windows\SYSVOL

These defaults are fine for a homelab environment.

## 5. Prerequisites Check

Before installing, the wizard performed a prerequisites check.
I reviewed the warnings, but there were no errors, so I proceeded with:

  Install

The system began promoting the server to a domain controller.
When it completed, the server rebooted automatically.

## 6. First Login to the New Domain

After the reboot, the login screen showed that the server was now part of the new domain.
I logged in using:

  JSUN\Administrator

This confirmed that the domain controller setup was successful.

## 7. Verifying the Installation

Once logged in, I opened:

- Active Directory Users and Computers  
- DNS Manager  
- Group Policy Management  

All tools were available and functional.
This means that the Windows Server installation, AD DS setup, and domain controller promotion were successful.
