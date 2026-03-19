## Day 14 - Linux Process Troubleshooting

## Task Details:
The production support team of xFusionCorp Industries has deployed some of the latest monitoring tools to keep an eye on every service, application, etc. running on the systems. One of the monitoring systems reported about Apache service unavailability on one of the app servers in Stratos DC.

Identify the faulty app host and fix the issue. Make sure Apache service is up and running on all app hosts. They might not have hosted any code yet on these servers, so you don't need to worry if Apache isn't serving any pages. Just make sure the service is up and running. Also, make sure Apache is running on port 6200 on all app servers.

## Steps:
1. Check all servers Apache status
    ```
    curl -Ik http://stapp01:6200
    curl -Ik http://stapp02:6200
    curl -Ik http://stapp03:6200
    ```

2. SSH into faulty host and switch to root user 
    ```
    ssh tony@stapp01
    sudo -i
    ```

3. Check Apache status
    ```
    systemctl status httpd
    ```

4. Confirms Apache is listening on `6200`
    ```
    ss -tunap | grep 6200
    ```

5. If not, kill the service
    ```
    kill -9 <PID>
    ```

6. Restart the Apache service
    ```
    systemctl restart httpd
    ```

7. Go back to the jump host and verify:
    ```
    curl http://stapp01:6200
    ```



