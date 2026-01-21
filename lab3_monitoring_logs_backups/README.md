# Lab 3: Linux Monitoring, Log Analysis & Automated Backups (AWS)

## Goal
Monitor system health, analyze Linux logs, and implement automated backups using cron on an AWS EC2 Ubuntu server.

## Architecture
- Cloud Provider: AWS EC2 (Free Tier)
- Instance Type: t3.micro
- OS: Ubuntu 24.04.3 LTS
- Access Method: EC2 Instance Connect (Browser-based SSH)
- Network: Default VPC (Public Subnet)
- Monitoring Tools: htop, sysstat
- Automation: Bash scripts, cron

## Steps I Performed

1. Monitored system performance and resource usage.  
   - Checked CPU load, memory usage, uptime, and running processes using `uptime`, `free`, `df`, and `htop`.  
   - Screenshot: [system-metrics](./screenshots/system_metrics.png)

2. Created a disk usage alert script.  
   - Wrote a Bash script to check root disk usage and alert when usage exceeds a defined threshold.  
   - Executed script to validate output.  
   - Screenshot: [disk-alert](./screenshots/disk_alert.png)

3. Analyzed SSH logs using journalctl.  
   - Reviewed recent SSH service activity to validate log visibility and access events.  
   - Screenshot: [journalctl-ssh](./screenshots/journalctl_ssh.png)

4. Created an automated backup script for system configuration files.  
   - Developed a Bash script to compress and store `/etc` backups with timestamps.  
   - Screenshot: [backup-script](./screenshots/backup_script.png)

5. Executed and verified backup creation.  
   - Confirmed successful creation of compressed backup files in the backups directory.  
   - Screenshot: [backup-results](./screenshots/backup_results.png)

6. Scheduled automated daily backups using cron.  
   - Configured a cron job to run the backup script daily at 1:00 AM and log output.  
   - Verified cron configuration.  
   - Screenshot: [cron-job](./screenshots/cron_job.png)

## Key Findings
- System monitoring tools provide real-time visibility into server health and performance.
- Bash scripting enables lightweight automation for operational tasks.
- Log analysis using `journalctl` is essential for troubleshooting and auditing access.
- Automated backups reduce risk of configuration loss and improve system resilience.
- Cron jobs provide reliable scheduling for recurring administrative tasks.

## Screenshots & Commands
- System Metrics: [Screenshot](./screenshots/system_metrics.png)
- Disk Usage Alert Script: [Screenshot](./screenshots/disk_alert.png)
- SSH Log Analysis: [Screenshot](./screenshots/journalctl_ssh.png)
- Backup Script: [Screenshot](./screenshots/backup_script.png)
- Backup Results: [Screenshot](./screenshots/backup_results.png)
- Cron Job Configuration: [Screenshot](./screenshots/cron_job.png)
