## Part 1: Linux File System Hierarchy

#### / = It is a root directory, the very top of the entire filesystem hierarchy.
#### /home =  The base directory where the system stores personal files and settings for all regular users.
#### /root = It is root directory where only root can access.
#### /etc= It is used to store configuration file system and also uses to store the password.
#### /var/log = It is the dreictory where system stores the log files and it is used to show the logs while debugging.
#### /tmp = It is used to store the temporary file. where we can store installation files.

## Additional Directories

#### /bin = contains executables needed for the system to work.
#### /usr/bin = It contains most of the user command executables and application binaries.
#### /opt = It is a directory used for installing optional or third-party software packages.

## Scenario-Based Practice

### Scenario 1: Service not starting
#### step 1: 
##### systemctl status nginx: Check the service is running or failed.
#### step 2:
##### systemctl is-enabled nginx: Check if the service restart after the reboot.
#### step 3:
##### journalctl -u nginx -n 50: Check the logs of last 50 lines.

### Scenario 2: High CPU Usage
#### step 1:
##### top: Shows the live CPU usage.
#### step 2 : 
##### ps aux --sort=-%cpu | head -10: Sort the processes by CPU percentage. Note down PID of top processes.
#### step 3: 
##### kill <PID>: can kill the CPU pid.

### Scenario 3: Finding Service Logs
#### step 1: 
##### systemctl status docker: Check the service is running or failed.
#### step 2: 
##### journalctl -u docker -n 10: Check the logs of last 10 lines.

### Scenario 4: File Permissions Issue
#### step 1:
##### ls -l demo.sh: Check current permissions of file. Look for: -rw-r--r-- (notice no 'x' = not executable).
#### step 2: 
##### chmod +x demo.sh: Add execute permission to file.
#### Step 3: 
##### ls -l demo.sh: Verify it worked. Look for: -rwxr-xr-x
#### Step 4: 
##### ./demo.sh: Run it.
