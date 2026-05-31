# 🏠 Home IT Lab — Enterprise Environment

A fully functional enterprise-grade homelab built on VMware Workstation Pro, designed to simulate real-world IT infrastructure with a focus on **patch management**, **endpoint management**, and **Windows Server administration**.

> Built to develop and demonstrate hands-on skills in SCCM/MECM, WSUS, Active Directory, and infrastructure automation.

---

## 📐 Network Overview

| Role | Hostname | OS | IP Address |
|------|----------|----|------------|
| Domain Controller + DNS | DC1 | Windows Server 2022 | 192.168.5.180 |
| WSUS | WSUS | Windows Server 2022 | 192.168.5.181 |
| File Server | FILESERVER | Windows Server 2025 | 192.168.5.182 |
| SCCM/MECM | SCCM | Windows Server 2025 | 192.168.5.185 |
| Ansible | ansible | Fedora 44 Server | 192.168.5.186 |
| Ubuntu Server | ubuntu_lts | Ubuntu Server 26.04 LTS | 192.168.5.187 |
| Win11 HR Workstation 1 | WIN11HR1 | Windows 11 | 192.168.5.170 |
| Win11 HR Workstation 2 | WIN11HR2 | Windows 11 | 192.168.5.172 |
| Win10 Mgmt Workstation 1 | WIN10MGMT1 | Windows 10 | 192.168.5.171 |
| Win10 Mgmt Workstation 2 | WIN10MGMT2 | Windows 10 | 192.168.5.173 |

> All VMs run on **VMware Workstation Pro** on a single physical host.

<img width="1916" height="1151" alt="image" src="https://github.com/user-attachments/assets/ba377a75-4dac-487b-b502-0da977f08f66" />

---

## 🗂️ Active Directory Structure

```
homelab.local
│
├── OU=HomeLab-Servers
│   ├── OU=Windows
│   └── OU=Linux
│
├── OU=HomeLab-Workstations
│   ├── OU=Pilot        ← WIN11HR1, WIN11HR2
│   └── OU=Production   ← WIN10MGMT1, WIN10MGMT2
│
├── OU=HomeLab-Users
│   ├── OU=IT
│   ├── OU=HR
│   └── OU=Management
│
├── OU=HomeLab-Groups
└── OU=HomeLab-ServiceAccounts
```

---

## 🔧 What's Covered

| Area | Technology | Status |
|------|-----------|--------|
| Identity & Directory | Active Directory, DNS | ✅ Done |
| Patch Management (WSUS) | WSUS, GPO, Deployment Rings | ✅ Done |
| Patch Management (MECM) | SCCM/MECM, SUP, Collections | ✅ Done |
| File Services | Windows File Server, NTFS/Share Permissions | ✅ Done |
| Software Deployment | MECM Application Deployment (7-Zip) | ✅ Done |
| Automation | Ansible (Fedora 44) | 🔄 In Progress |
| Linux Server | Ubuntu Server 26.04 LTS | 🔄 In Progress |

---

## 📁 Repository Structure

```
├── 01-Active-Directory/     Domain setup, OU structure, GPO, groups
├── 02-WSUS/                 WSUS setup, sync fixes, deployment rings
├── 03-File-Server/          Shares, NTFS permissions, AD groups
├── 04-MECM-SCCM/            Full MECM deployment: SUP, collections, patching, app deployment
├── 05-Ansible/              Ansible server setup and playbooks
└── docs/                    Network diagram, architecture notes
```

---

## 💡 Key Skills Demonstrated

- End-to-end **patch lifecycle management** (planning → testing → deployment → reporting)
- **WSUS** configuration, troubleshooting deadlocks, deployment ring separation
- **MECM/SCCM** primary site installation, Software Update Point, device collections, application deployment
- **Active Directory** — OU design, GPO, group management, schema extension
- **PowerShell** for automation and configuration
- **Troubleshooting** real-world issues (WSUS SQL deadlocks, MECM SQL Express compatibility, client push failures)

---

## ➡️ Start Here

→ [01 — Active Directory](./01-Active-Directory/README.md)
→ [02 — WSUS Patch Management](./02-WSUS/README.md)
→ [03 — File Server](./03-File-Server/README.md)
→ [04 — MECM/SCCM](./04-MECM-SCCM/README.md)
→ [05 — Ansible](./05-Ansible/README.md)
