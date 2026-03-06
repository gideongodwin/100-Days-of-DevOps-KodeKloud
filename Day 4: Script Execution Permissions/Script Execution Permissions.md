## Day 4: Script Execution Permissions

#### Task Details:

In a bid to automate backup processes, the `xFusionCorp Industries` sysadmin team has developed a new bash script named `xfusioncorp.sh` While the script has been distributed to all necessary servers, it lacks executable permissions on App Server 3 within the Stratos Datacenter
Your task is to grant executable permissions to the `/tmp/xfusioncorp.sh` script on `App Server 3` Additionally, ensure that all users have the capability to execute it.

#### STEPS: 
1. Connect to the First App Server \
   `ssh banner@stapp03`
- When prompted, enter the password for user `banner`

2. Switch to Root User \
   `sudo -i`

3. Check the existing permissions of the script \
   `ls -l /tmp/xfusioncorp.sh`

4. Grant Execute Permission to All Users \
   `chmod +rx /tmp/xfusioncorp.sh`

5. Verify that the script is now executable \
   `ls -l /tmp/xfusioncorp.sh`

6. Exit the server
   `exit`
