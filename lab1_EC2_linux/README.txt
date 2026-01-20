# Lab 1: Linux User Management, Sudo Configuration & SSH Hardening (AWS)

## Goal
Create and manage Linux users and groups, configure role-based sudo access, and validate SSH service configuration on an AWS EC2 Ubuntu server using Free Tier resources.

## Architecture
- Cloud Provider: AWS EC2 (Free Tier)
- Instance Type: t3.micro
- OS: Ubuntu 24.04.3 LTS
- Access Method: EC2 Instance Connect (Browser-based SSH)
- Network: Default VPC (Public Subnet)
- Users Created:
  - alice (opsadmin)
  - bob (opsadmin)
  - carol (opsadmin)

## Steps I Performed

1. Verified system information and network interfaces.  
   - Confirmed Ubuntu version, kernel, virtualization platform, and active network interface.  
   - Screenshot: [system-info](./screenshots/system-info.png)

2. Created role-based Linux groups.  
   - Created `opsadmin`, `devteam`, and `analytics` groups.  
   - Verified group creation using `getent group`.  
   - Screenshot: [groups-created](./screenshots/groups-created.png)

3. Created users and assigned group memberships.  
   - Created users `alice`, `bob`, and `carol`.  
   - Added users to the `opsadmin` group.  
   - Verified memberships using `id` command.  
   - Screenshot: [users-and-groups](./screenshots/users-and-groups.png)

4. Configured sudo privileges using `visudo`.  
   - Granted full sudo access to members of the `opsadmin` group using `%opsadmin ALL=(ALL:ALL) ALL`.  
   - Screenshot: [sudoers-config](./screenshots/sudoers-config.png)

5. Validated sudo access for non-root user.  
   - Switched to user `alice` and confirmed sudo access using `sudo whoami`.  
   - Screenshot: [sudo-test-alice](./screenshots/sudo-test-alice.png)

6. Verified SSH service configuration and status.  
   - Confirmed OpenSSH service was running and listening on port 22.  
   - Validated SSH is managed through AWS EC2 Instance Connect.  
   - Screenshot: [sshd-config](./screenshots/sshd-config.png)

## Key Findings
- Role-based groups simplify administrative access management.
- Delegating sudo privileges via group membership enforces least-privilege principles.
- Non-root administrative access was successfully validated.
- SSH service was active and correctly managed within the AWS EC2 environment.
- AWS Security Groups provide an additional network-layer control for SSH access.

## Screenshots & Commands
- System Info: [Screenshot](./screenshots/system-info.png)
- Groups Created: [Screenshot](./screenshots/groups-created.png)
- Users & Groups: [Screenshot](./screenshots/users-and-groups.png)
- Sudoers Configuration: [Screenshot](./screenshots/sudoers-config.png)
- Sudo Test (alice): [Screenshot](./screenshots/sudo-test-alice.png)
- SSH Service Status: [Screenshot](./screenshots/sshd-config.png)
