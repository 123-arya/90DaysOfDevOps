# Day 02 – Linux Architecture, Processes, and systemd

## core components of Linux

### 1. Kernel

The kernel is the core of the Linux operating system, acting as a bridge between the software and the physical hardware. It has complete control over system resources and manages crucial functions:
  - Process Management: The kernel handles the creation, scheduling, and termination of processes, efficiently distributing CPU time among     running programs.
  - Memory Management: It manages system memory, including physical and virtual memory, ensuring efficient use of available resources.
  - Device Management: The kernel includes device drivers that interface with hardware components like storage devices, network cards, and     input/output devices.
  - File System Management: It provides a unified interface, the Virtual File System (VFS), to access data stored on various types of          storage media.
  - Networking: The kernel manages network communications, implementing protocols like TCP/IP.

### 2. User Space

User space refers to the collection of software and libraries that run "on top" of the kernel. The kernel protects its memory space from user space processes, which run in their own virtual address spaces. Key components include:
  - System Libraries: These are collections of functions (e.g., the GNU C Library, glibc) that applications use to make system calls and        interact with the kernel.
  - Shell/User Interface: The interface through which users interact with the system, either a command-line interface (CLI) like Bash, or      a graphical user interface (GUI).
  - System Utilities: Programs designed to perform system management tasks, such as file manipulation (ls, cp, mv) and process management      (ps, kill).
  - Application Programs: All user-facing software, such as web browsers, office suites, and development tools, runs in user space.

### 3. Init System

The init process is the first user-mode process started by the kernel after the system boots (it is assigned Process ID 1, or PID 1). Its primary role is to initialize the user space and start all other system services and daemons.
  - systemd: Modern Linux systems primarily use systemd as the init system. It manages the boot process by starting services in parallel,      using configuration files called "units" (services, sockets, mount points, etc.) and "targets" (groups of units for a specific system      state, like graphical.target or multi-user.target).
  - SysV init: The traditional, older initialization system that systemd has largely replaced. systemd maintains backward compatibility        with SysV init scripts.

### Process Creation

A new process is created using the fork() system call. When fork() is invoked, the operating system creates a child process that is an almost exact copy of the parent process. Both processes continue execution from the same point, but they have different process IDs (PIDs).

After creation, the child process usually calls the exec() system call to replace its memory space with a new program. This allows the child to run a different executable while keeping the same PID.

### Process Termination

When a process finishes execution, it terminates and returns an exit status. The parent process calls wait() or waitpid() to collect this status. This step is important to prevent zombie processes, which are terminated processes that still occupy entries in the process table.

Linux processes move through different states such as:
Running – currently executing on the CPU
Sleeping – waiting for an event or I/O
Stopped – paused by a signal
Zombie – finished execution but not yet cleaned up

## Why systemd Matters for DevOps
Start/stop services (nginx, docker, databases)
Check service status
View logs
Set services to start on boot
Troubleshoot why services failed

## Essential systemd Commands

- Start a service
    sudo systemctl start nginx
  
- Stop a service
    sudo systemctl stop nginx
  
- Restart a service
    sudo systemctl restart nginx
  
- Check status
    sudo systemctl status nginx
  
- Enable (start on boot)
    sudo systemctl enable nginx
  
- Disable (don't start on boot)
    sudo systemctl disable nginx
  
- View logs for a service
    sudo journalctl -u nginx
  
View real-time logs
  sudo journalctl -u nginx -f
  
List all running services
  systemctl list-units --type=service --state=running
  
Check if a service failed
  systemctl is-failed nginx
