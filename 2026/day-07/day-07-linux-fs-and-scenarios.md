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
##### systemctl status myapp: Check the service is running or failed.


#### step 3:
##### journalctl -u myapp -n 50: Check the logs of last 50 lines.
##### 
