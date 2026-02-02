# File Permissions & File Operations Challenge

## Task 1: Create Files

- touch devops.txt
- touch notes.txt
- cat notes.txt
- vim script.sh
- echo "Hello DevOps"

ls -l: to see the permissions

## Task 2: Read Files

- cat notes.txt
- sudo chmod 400 script.sh
- vim script.sh
- head -n 5 /etc/passwd
- tail -n 5 /etc/passwd

## Task 3: Understand Permissions

ls -l 
- devops.txt: -rw-rw-r-- (owner and group has read write permission)
- notes.txt: -rw-rw-r-- (owner and group has read write permission)
- script.sh: -r-------- (owner has read permission)

## Task 4: Modify Permissions

ls -l
- devops.txt: -r--r--r--     (owner and group has read write permission)
- notes.txt: -rw-r-----  (owner and group has read write permission)
- script.sh: -r-xr-xr-x (owner has r,x group has r,x other users has r,x)
- project: drwxr-xr-x (owner has w,r,x group has r,x other users has r,x)

## Task 5: Test Permissions

1. writing to a read-only file - what happens?      -- INSERT -- W10: Warning: Changing a readonly file   
2.ubuntu@ip-172-31-13-222:~$ sudo chmod -w notes.txt
  ubuntu@ip-172-31-13-222:~$ ./notes.txt
  -bash: ./notes.txt: Permission denied

## What I Learned
How to change the permission
How to execute
How to create a file
