# Linux Practice: Processes and Services

## Process Commands

- ps: Display the current process
- top: Displa the linux processes
- kill -9 <PID>: kill the process

## Service Commands
- sudo systemctl status docker: Checks the docker is active or not.
- sudo systemctl start docker: Checks if docker is started.
- sudo systemctl enable docker: Configures the docker service automatically start at th boot time.
- sudo systemctl stop docker: Stop the docker service.

## Log Check Commands

- journalctl: Allow to view all system logs.
- tail -n 50: Shows the last 50 lines of logs.
- journalctl -u: Shows the logs for a specific systemd service.
