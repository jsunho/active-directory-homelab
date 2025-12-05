# active-directory-homelab
A small virtual lab that sets up an on-premises Active Directory domain with a domain controller, Windows client, and basic enterprise features: OUs, users, groups, Group Policies, and file shares with proper permissions. The project is fully documented and reproducible on a single host machine.

# Active Directory Homelab

This repository documents a small virtual **Active Directory** homelab running on a single host machine.  
The goal is to simulate a tiny on-premises enterprise environment with:

- One **Domain Controller** (DC01)
- One **Windows client** (CLIENT01)
- A clean **OU / group / user** structure
- **Group Policies** for basic security hardening
- **File shares** with proper permissions

All steps are documented and reproducible.

---

## 1. Lab Goals

This project is meant to:

- Practice installing and configuring **Active Directory Domain Services (AD DS)**
- Understand **domain join**, **DNS integration**, and **name resolution**
- Design a simple but realistic **OU structure** for a small company
- Implement **Group Policies** for:
  - Password and account lockout policies
  - Local security hardening
  - Login messages, desktop restrictions, etc.
- Configure **file shares** and NTFS permissions using a role-based approach

Optional stretch goals:

- Add a **dedicated file server** (FS01)
- Add a **Linux client** authenticating against AD
- Integrate additional roles (NPS / RADIUS, WSUS, WDS, etc.)

---

## 2. Requirements

- Host machine with virtualization support
- Virtualization software of your choice (e.g. UTM, VirtualBox, VMware, etc.)
- Windows Server ISO (evaluation is fine)
- Windows 10 / 11 ISO (evaluation is fine)
- ~4–8 GB RAM free for lab VMs
- ~80–100 GB disk space available (to be safe)

---

## 3. Project Structure

.
├── README.md
├── docs/
│   ├── 01_lab-overview.md
│   ├── 02_virtualization-setup.md
│   ├── 03_install_windows_server.md
│   ├── 04_create-ou-structure-and-users.md
│   ├── 05_join-client01-to-domain.md
│   ├── 06_group-policy-baseline.md
│   ├── 07_file-shares-and-permissions.md
│   └── 08_optional-extensions.md
├── diagrams/
├── config/
│   ├── gpo-backups/
│   └── powershell/
└── screenshots/
