# Lab 2: SSH Hardening, Firewall Configuration & Fail2Ban (AWS)

## Goal
Harden SSH access, configure a host-based firewall, create a non-root administrative user, and deploy Fail2Ban to protect an AWS EC2 Ubuntu server from unauthorized access attempts.

## Architecture
- Cloud Provider: AWS EC2 (Free Tier)
- Instance Type: t3.micro
- OS: Ubuntu 24.04.3 LTS
- Access Method: EC2 Instance Connect (Browser-based SSH)
- Network: Default VPC (Public Subnet)
- Firewall: UFW (host-based)
- Security Tool: Fail2Ban

## Steps I Performed

1. Created a dedicated non-root administrative user.  
   - Added `adminuser` and assigned sudo privileges.  
   - Verified group membership using the `id` command.  
   - Screenshot: [adminuser-id](./screenshots/adminuser_id.png)

2. Backed up the SSH daemon configuration file.  
   - Created a backup of `/etc/ssh/sshd_config` before making changes.  
   - Screenshot: [sshd-backup](./screenshots/sshd_backup.png)

3. Hardened SSH configuration.  
   - Validated SSH configuration syntax using `sshd -t`.  
   - Restarted SSH service and confirmed active status.  
   - Screenshot: [sshd-hardening](./screenshots/sshd_hardening.png)

4. Enabled and configured UFW firewall.  
   - Allowed inbound SSH traffic on port 22.  
   - Enabled UFW and confirmed default deny inbound policy.  
   - Screenshot: [ufw-status](./screenshots/ufw_status.png)

5. Installed and enabled Fail2Ban service.  
   - Installed Fail2Ban using apt package manager.  
   - Enabled service at startup and confirmed running status.  
   - Screenshot: [fail2ban-running](./screenshots/fail2ban_running.png)

## Key Findings
- Creating a non-root administrative user reduces reliance on the root account.
- SSH configuration validation prevents accidental lockouts.
- UFW provides an effective host-based firewall layer in addition to AWS Security Groups.
- Fail2Ban adds automated protection against brute-force SSH attempts.
- Layered security controls significantly reduce the server attack surface.

## Screenshots & Commands
- Admin User Verification: [Screenshot](./screenshots/adminuser_id.png)
- SSH Config Backup: [Screenshot](./screenshots/sshd_backup.png)
- SSH Service Validation: [Screenshot](./screenshots/sshd_hardening.png)
- UFW Firewall Status: [Screenshot](./screenshots/ufw_status.png)
- Fail2Ban Service Status: [Screenshot](./screenshots/fail2ban_running.png)
