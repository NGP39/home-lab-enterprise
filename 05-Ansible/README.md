# 05 — Ansible

**Server:** ansible | Fedora 44 Server | IP: 192.168.5.186  
**Domain:** homelab.local (joined via Cockpit)

---

## Overview

Ansible is included in the lab as the Linux-based automation layer. The server is joined to the `homelab.local` domain and managed via the Cockpit web console.

> 🔄 This section is in progress. Planned content: inventory configuration, example playbooks for Windows endpoint management, and integration with the existing AD/MECM environment.

---

## Setup

```bash
sudo dnf install ansible
```

Cockpit web console available at: `https://192.168.5.186:9090`

---

## Planned Playbooks

- [ ] Windows update status check across domain-joined endpoints
- [ ] Service status reporting (WSUS, MECM agent)
- [ ] Basic AD user provisioning

📷 *Screenshot: Cockpit web console showing Ansible server joined to homelab.local*

