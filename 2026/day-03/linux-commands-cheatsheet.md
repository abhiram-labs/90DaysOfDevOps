# Linux Commands Cheat Sheet – Day 03

**Challenge:** 90DaysOfDevOps  
**Topic:** Linux Command Practice  
**Purpose:** Process Management, File System & Networking Troubleshooting

---

## 1. Process Management Commands

| Command | Usage |
|---|---|
| `ps aux` | Displays all running processes. |
| `top` | Monitors running processes and system resource usage in real time. |
| `htop` | Provides an interactive process monitoring interface (if installed). |
| `pgrep nginx` | Finds the process ID of a process by name. |
| `kill PID` | Sends a termination signal to a process. |
| `kill -9 PID` | Forcefully terminates a process (use only when necessary). |
| `pkill nginx` | Terminates processes matching a name. |
| `jobs` | Lists jobs running in the current shell. |
| `bg` | Resumes a suspended job in the background. |
| `fg` | Brings a background job to the foreground. |
| `nice -n 10 command` | Starts a process with a specified scheduling priority. |
| `renice 5 -p PID` | Changes the scheduling priority of an existing process. |

**Useful example:**

```bash
ps aux | grep nginx
```

Finds processes related to Nginx.

---

## 2. File System Commands

| Command | Usage |
|---|---|
| `pwd` | Displays the current working directory. |
| `ls` | Lists files and directories. |
| `ls -lah` | Lists files, including hidden files, with detailed information and readable sizes. |
| `cd /path` | Changes the current directory. |
| `mkdir test` | Creates a new directory. |
| `touch file.txt` | Creates an empty file or updates its timestamp. |
| `cp file.txt backup.txt` | Copies a file. |
| `mv old.txt new.txt` | Moves or renames a file. |
| `rm file.txt` | Deletes a file. |
| `rmdir test` | Removes an empty directory. |
| `cat file.txt` | Displays file contents. |
| `less file.txt` | Views large files page by page. |
| `head -n 10 file.txt` | Displays the first 10 lines of a file. |
| `tail -n 10 file.txt` | Displays the last 10 lines of a file. |
| `tail -f /var/log/syslog` | Continuously monitors new log entries. |
| `grep "error" file.txt` | Searches for a specific word or pattern in a file. |
| `find /var/log -name "*.log"` | Finds log files in a directory. |
| `chmod 755 script.sh` | Changes file permissions. |
| `chown user:group file.txt` | Changes file ownership. |
| `df -h` | Displays available and used disk space. |
| `du -sh /var/log` | Displays the total size of a directory. |
| `tar -czf backup.tar.gz folder/` | Creates a compressed archive of a directory. |

**Useful examples:**

```bash
# Monitor logs in real time
tail -f /var/log/syslog

# Search for errors in a log file
grep -i "error" /var/log/syslog

# Check disk usage
df -h

# Find large directories
du -sh /var/log
```

---

## 3. Networking Troubleshooting Commands

| Command | Usage |
|---|---|
| `ping google.com` | Checks network connectivity to a destination. |
| `ip addr` | Displays network interfaces and their IP addresses. |
| `ip route` | Displays the system's routing table. |
| `dig google.com` | Queries DNS records for a domain. |
| `curl -I https://google.com` | Checks HTTP response headers from a website. |
| `ss -tulnp` | Displays listening TCP/UDP sockets and associated processes (where permitted). |
| `traceroute google.com` | Displays the network path to a destination (if installed). |

**Useful examples:**

```bash
# Check internet connectivity
ping -c 4 google.com

# Find your IP address
ip addr

# Check DNS resolution
dig google.com

# Check website response
curl -I https://google.com

# Check listening ports
ss -tulnp
```

---

## 4. Important Linux Log Troubleshooting Tips

Logs are important when troubleshooting production issues.

| Command | Usage |
|---|---|
| `journalctl` | Displays systemd journal logs. |
| `journalctl -u nginx` | Displays logs for the Nginx service. |
| `journalctl -f` | Follows system logs in real time. |
| `dmesg` | Displays kernel-related messages. |

**Useful example:**

```bash
# Check Nginx service logs
journalctl -u nginx -n 50

# Monitor system logs continuously
journalctl -f
```

---

## 5. Quick Troubleshooting Workflow

When a Linux server experiences an issue, these commands can help:

1. Check running processes:

   `top`

2. Check memory usage:

   `free -h`

3. Check disk space:

   `df -h`

4. Check system logs:

   `journalctl -xe`

5. Check network configuration:

   `ip addr`

6. Test network connectivity:

   `ping -c 4 google.com`

7. Check listening ports:

   `ss -tulnp`

---

## 6. Important Notes

- Use `sudo` when administrative privileges are required.
- Be careful when using `rm` and `kill -9`.
- Prefer `kill PID` before forcefully terminating a process.
- Use `man command` to read the manual for any Linux command.
- Use `command --help` to quickly understand available options.

**Example:**

```bash
man ls
man chmod
man systemctl
```

---

## 7. What I Learned Today

- How to inspect and manage Linux processes.
- How to navigate directories and manage files.
- How to monitor disk usage and permissions.
- How to troubleshoot basic network connectivity.
- How to inspect system and application logs.

**Day 03 Status:** Completed – Linux Commands Practice.

#90DaysOfDevOps #DevOpsKaJosh #TrainWithShubham