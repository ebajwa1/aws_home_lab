# AWS Linux Security & Administration Home Lab (Ubuntu on EC2)

Hands-on portfolio project built to develop and showcase **Linux system administration and security skills in a cloud environment**.  
This lab series demonstrates practical experience with **user and group management, SSH hardening, firewall configuration, monitoring, logging, and automation** using AWS Free Tier resources.

All labs were performed on **Ubuntu Server running on AWS EC2**, with step-by-step procedures, commands, screenshots, and documented findings suitable for **Junior Linux Administrator** and **Cloud Support** roles.

---

## Architecture
- **Cloud Provider:** Amazon Web Services (AWS)
- **Compute:** EC2 (Free Tier)
- **Instance Type:** t3.micro
- **Operating System:** Ubuntu Server 24.04 LTS
- **Access Method:** EC2 Instance Connect (Browser-based SSH)
- **Networking:**
  - Default VPC
  - Public subnet
  - Security Groups controlling SSH access
- **Cost:** $0 (AWS Free Tier only)

---

## Labs

### **Lab 1: Linux User Management, Sudo Configuration & SSH Hardening (AWS)**
**Goal:** Create and manage Linux users and groups, configure role-based sudo access, and validate secure SSH access on an AWS EC2 Ubuntu server.

- Created Linux users and role-based groups
- Assigned group memberships and validated access using `id`
- Configured sudo privileges securely with `visudo`
- Verified non-root administrative access
- Validated SSH service status and access through EC2 Instance Connect
- Documented configuration and access validation with screenshots

Folder: `/Lab-01-User-Management-AWS`

---

### **Lab 2: SSH Hardening, Firewall Configuration & Fail2Ban (AWS)**
**Goal:** Harden SSH access and implement layered security controls to reduce attack surface on a cloud-based Linux server.

- Created a dedicated non-root administrative user
- Backed up and validated SSH daemon configuration
- Restarted and verified SSH service integrity
- Enabled and configured UFW host-based firewall
- Deployed Fail2Ban to protect against brute-force SSH attempts
- Verified services were active and enforced at startup

Folder: `/Lab-02-SSH-Hardening-UFW-Fail2Ban-AWS`

---

### **Lab 3: Linux Monitoring, Log Analysis & Automated Backups (AWS)**
**Goal:** Monitor system health, analyze logs, and automate backups using Bash scripting and cron.

- Monitored CPU, memory, disk usage, and processes using `uptime`, `free`, `df`, and `htop`
- Created a disk usage alert script using Bash
- Analyzed SSH service logs using `journalctl`
- Developed a backup script for critical configuration files (`/etc`)
- Scheduled automated daily backups using cron
- Verified backup creation and logging

Folder: `/Lab-03-Monitoring-Logs-Backups-AWS`

---

## How to Use This Repository
Each lab folder contains:
- Clear lab objectives and architecture
- Step-by-step procedures performed on AWS EC2
- Terminal commands and configuration changes
- Screenshots with descriptive filenames
- Key findings and operational/security observations

---

## Skills Demonstrated
- Linux user and group administration
- Role-based sudo access control
- SSH service validation and hardening
- Host-based firewall configuration (UFW)
- Intrusion mitigation with Fail2Ban
- System monitoring and resource analysis
- Linux log analysis using `journalctl`
- Bash scripting for automation
- Scheduled tasks with cron
- Cloud-based Linux administration (AWS EC2)

---

## Notes
This lab environment reflects **real-world cloud administration scenarios**, emphasizing:
- Secure configuration
- Validation and testing
- Troubleshooting and recovery
- Accurate documentation over idealized setups

All work was completed using **AWS Free Tier resources**, with cost controls in place to prevent unintended charges.
