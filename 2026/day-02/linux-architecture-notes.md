# Day 02: Linux Architecture, Processes, and systemd

## 1. Linux Architecture
- **Kernel:** The core of Linux. It manages CPU, memory, processes, and hardware devices.
- **User space:** The environment where applications and commands run. They request privileged operations from the kernel through system calls.
- **Boot process:** The kernel initializes the system and starts the first userspace process, usually `systemd` (PID 1) on Ubuntu.

## 2. Programs and Processes
- A **program** is stored instructions; a **process** is an executing instance of a program.
- Each process has a Process ID (PID) and a Parent Process ID (PPID).
- A shell can create child processes to run commands. For example, Bash launches `ps -ef`.
- Process creation commonly involves `fork()`, `execve()`, and `wait()`; a process can finish with `exit()`.

## 3. Process States
- `R`: Running or ready to run.
- `S`: Interruptible sleep, waiting for an event.
- `D`: Uninterruptible sleep, often waiting for I/O.
- `T`: Stopped.
- `Z`: Zombie; execution has finished, but the parent has not collected the exit status.

## 4. systemd and Services
- `systemd` is commonly PID 1 on Ubuntu and manages system services.
- A process is a running program; a service is a managed background function that may use one or more processes.
- `systemctl status ssh` checks the SSH service status.
- `systemctl start`, `restart`, `enable`, and `disable` change service state or startup behavior. Avoid restarting SSH on a remote server without a safe access plan.

## 5. Five Useful Commands
- `pwd` — show the current directory.
- `ls` — list directory contents.
- `cd` — change directory.
- `ps -ef` — list processes.
- `systemctl status ssh` — inspect the SSH service.

## Practical Learning
I checked PID 1 with `ps -p 1 -o pid,comm,args` and saw `systemd` with `/sbin/init`. I inspected process IDs and parent-child relationships using `ps -ef`, and checked the SSH service with `systemctl status ssh`.