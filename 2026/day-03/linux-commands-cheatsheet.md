# Linux Command Cheat Sheet

## Process Management
1. ps aux - Shows all running processes with CPU & memory usage.
2. top - Real time processing monitoring.
3. kill -9 PID - Force kill a process.\
4. ps aux | grep nginx -Find the process by name.

## File System
1. pwd - prints working directory.
2. ls -l - lists files.
3. ls -la - lists hidden files also.
4. cd /path - change directory.
5. touch - create a empty file.
6. cp - copy the file or directory.
7. mv - move or rename the file or directory.
8. rm - delete the file.
9. rm -f - delete the directory.
10. cat - display the file content.
11. tail -f - live log monitoring.
12. chmod - change file permissions.
13. chown - change the ownership of file

 ## Network Troubleshooting
 1. ip addr - show teh ip address.
 2. ping google.com - test network connectivity.
 3. curl http://google.com - test http connectivity
 4. lsof -i :80 - Check which process is using a port.
 5. nslookup google.com - Check DNS configuration.
