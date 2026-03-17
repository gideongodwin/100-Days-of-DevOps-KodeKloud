## Day 3: Secure Root SSH Access

## Task Details:
- Disable direct SSH root login on all app servers within the `Stratos Datacenter`

## STEPS:

1. Log into the first app server and switch to root user
    ```
    ssh tony@stapp01
    sudo -i
    ```
    > When prompted, enter the password for user `tony`

2. Open the SSH Configuration File
   ```
   vi /etc/ssh/sshd_config
   ```

3. Modify the Root Login Setting
   - Find the line: PermitRootLogin `yes`
   - Change it to: PermitRootLogin `no`
  
4. Save the File
    ```
    :wq
    ```

5. Restart the SSH Service
    ```
    systemctl restart sshd`
    ```
6. Exit the server
```
exit
```
7. Repeat steps 1 to 6 for the remaining servers
   
