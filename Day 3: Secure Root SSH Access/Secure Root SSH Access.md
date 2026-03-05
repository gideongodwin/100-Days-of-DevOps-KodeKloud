## Day 3: Secure Root SSH Access

#### Task Details:
Following security audits, the `xFusionCorp Industries` security team has rolled out new protocols, including the restriction of direct root SSH login.
Your task is to disable direct SSH root login on all app servers within the `Stratos Datacenter`

#### STEPS:
1. Connect to the First App Server \
   `ssh tony@stapp01`
- When prompted, enter the password for user `tony`

2. Switch to Root User \
   `sudo -i`

3. Open the SSH Configuration File \
   `vi /etc/ssh/sshd_config`

4. Modify the Root Login Setting
   - Find the line: PermitRootLogin `yes`
   - Change it to: PermitRootLogin `no`
  
5. Save the File \
   `:wq`

6. Restart the SSH Service
   `systemctl restart sshd`

7. Exit the server
   `exit`

8. Repeat steps 1 to 7 for the remaining servers:
   
