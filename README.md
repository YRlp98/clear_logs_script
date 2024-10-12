# Log Clearing Script with Cron Job

This repository contains a simple bash script to clear the contents of a log file every week using a cron job. It is useful for managing log sizes and ensuring logs do not grow indefinitely.

## Requirements
- Ubuntu or any Linux distribution with cron enabled.
- Basic shell scripting knowledge.
- Access to the server or system where logs are stored.

## Steps to Set Up

### 1. Create the Log-Clearing Script

1. Navigate to the directory where you want to store the script:
    ```bash
    cd /home/ubuntu
    ```

2. Create the bash script:
    ```bash
    nano clear_logs.sh
    ```

3. Add the following content to the file:
    ```bash
    #!/bin/bash
    # This script clears the contents of eventLog.txt
    
    > /home/ubuntu/LiveDataChannel/logs/eventLog.txt
    ```

4. Save and close the file (`Ctrl + O`, then `Enter`, followed by `Ctrl + X`).

5. Make the script executable:
    ```bash
    chmod +x clear_logs.sh
    ```

### 2. Schedule the Script with Cron

1. Open the crontab editor:
    ```bash
    crontab -e
    ```

2. Add the following cron job to run the script every week (e.g., every Sunday at midnight):
    ```bash
    0 0 * * 0 /home/ubuntu/clear_logs.sh
    ```

3. Save and close the crontab.

### 3. Verify the Cron Job

You can verify that the cron job is set up correctly by listing all cron jobs:
```bash
crontab -l
```

### 4. Test the Script
To test that the script works as expected, you can manually run it:
    ```bash
    /home/ubuntu/clear_logs.sh
    ```

    

