# 03 — File Server

**Server:** FILESERVER | Windows Server 2025 | IP: 192.168.5.182

---

## Overview

A dedicated file server hosting department-based shared folders with access controlled through Active Directory security groups. Permissions follow the **AGDLP** principle — user accounts are placed in Global groups, which are then assigned permissions on resources.

---

## Share Structure

```
E:\Shares\
├── IT\
├── HR\
├── Management\
└── Public\
```

Created with:
```powershell
New-Item -Path "E:\Shares\IT","E:\Shares\HR","E:\Shares\Management","E:\Shares\Public" -ItemType Directory -Force
```

---

## AD Groups for File Access

Created in `OU=HomeLab-Groups`:

| Group | Access Level | Assigned To |
|-------|-------------|-------------|
| GG_IT_RW | Read/Write | IT share |
| GG_HR_RW | Read/Write | HR share |
| GG_Management_RW | Read/Write | Management share |
| GG_Public_RW | Read/Write | Public share |
| GG_IT_RO | Read Only | IT share |
| GG_HR_RO | Read Only | HR share |

**Group membership:**

| Group | Members |
|-------|---------|
| GG_IT_RW | jszwed, mkowalski |
| GG_HR_RW | anowak, kzielinska |

---

## Permissions

Each share follows the same permission model. Here's the example for `\\FILESERVER\HR`:

### Share Permissions
| Principal | Permission |
|-----------|-----------|
| Administrators | Full Control |
| Domain Users | Change, Read |
| Everyone | ❌ Removed |

### NTFS Permissions (Security tab)
| Principal | Permission |
|-----------|-----------|
| Domain Admins | Full Control |
| Administrators | Full Control |
| GG_HR_RW | Modify, Read & Execute, List Folder Contents, Read, Write |
| Everyone | ❌ Removed |

The same model applies to `\\FILESERVER\IT`, `\\FILESERVER\Management`, and `\\FILESERVER\Public`, with the corresponding `GG_*_RW` group assigned.

📷 *Screenshot: File Server — Explorer view showing E:\Shares with all 4 subfolders*

📷 *Screenshot: NTFS security tab for the HR folder showing group permissions*

---

## Notes

- `Everyone` was explicitly removed from both Share and NTFS permissions on all shares
- Access is managed entirely through AD group membership — adding/removing users from `GG_HR_RW` etc. controls their access without touching the server directly
