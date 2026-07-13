# Day 08 - Interview Questions (Linux File Management, Process Management & System Services)

## Basic Interview Questions

### 1. What is Linux?
**Answer:**
Linux is an open-source, Unix-like operating system used for servers, cloud computing, cybersecurity, and embedded systems.

---

### 2. What is the difference between a file and a directory?

**Answer:**
- A **file** stores data.
- A **directory** stores files and other directories.

---

### 3. How do you create a directory?

**Answer:**

```bash
mkdir directory_name
```

Example:

```bash
mkdir SOC
```

---

### 4. How do you create nested directories?

**Answer:**

```bash
mkdir -p SOC/L1
```

The `-p` option creates parent directories automatically if they don't exist.

---

### 5. How do you remove an empty directory?

**Answer:**

```bash
rmdir directory_name
```

---

### 6. How do you remove a directory that contains files?

**Answer:**

```bash
rm -rf directory_name
```

---

### 7. What does `rm -rf` mean?

**Answer:**
- `-r` → Recursive deletion
- `-f` → Force deletion without confirmation

---

### 8. What is the purpose of the `cat` command?

**Answer:**
It displays the contents of a file and can also concatenate multiple files.

---

### 9. What is the difference between `head` and `tail`?

**Answer:**
- `head` displays the first lines of a file.
- `tail` displays the last lines of a file.

---

### 10. How do you display the first five lines of a file?

**Answer:**

```bash
head -5 filename
```

---

### 11. How do you display the last five lines of a file?

**Answer:**

```bash
tail -5 filename
```

---

### 12. What is the purpose of the `man` command?

**Answer:**

It displays the manual page (documentation) of Linux commands.

Example:

```bash
man mkdir
```

---

## Intermediate Interview Questions

### 13. What is an absolute path?

**Answer:**

An absolute path starts from the root directory (`/`).

Example:

```text
/usr/share
```

---

### 14. What is a relative path?

**Answer:**

A relative path starts from the current working directory.

Example:

```text
Documents/Linux
```

---

### 15. Which command is preferred for checking IP addresses in modern Linux?

**Answer:**

```bash
ip addr
```

or

```bash
ip a
```

---

### 16. What is `ifconfig`?

**Answer:**

`ifconfig` is an older networking command used to display network interface information.

---

### 17. What does the `ping` command do?

**Answer:**

It checks network connectivity between two systems.

Example:

```bash
ping google.com
```

---

## Process Management Questions

### 18. What is a process?

**Answer:**

A process is a program that is currently running in memory.

---

### 19. Which command displays running processes?

**Answer:**

```bash
ps
```

---

### 20. What is the difference between `ps` and `ps aux`?

**Answer:**

- `ps` shows processes of the current terminal.
- `ps aux` shows all running processes with detailed information.

---

### 21. What does the `top` command do?

**Answer:**

It displays running processes in real time along with CPU and memory usage.

---

### 22. How do you find the Process ID (PID)?

**Answer:**

```bash
pgrep process_name
```

or

```bash
pidof process_name
```

---

### 23. How do you terminate a process?

**Answer:**

```bash
kill PID
```

---

### 24. What is `kill -9`?

**Answer:**

It forcefully terminates a process using signal 9 (SIGKILL).

---

### 25. What is the difference between `kill`, `pkill`, and `killall`?

**Answer:**

- `kill` → Terminates a process using its PID.
- `pkill` → Terminates a process using its name.
- `killall` → Terminates all processes with the specified name.

---

### 26. What does `kill -l` do?

**Answer:**

It lists all available kill signals.

---

## Service Management Questions

### 27. What is `systemctl`?

**Answer:**

`systemctl` is the command used to manage system services in Linux.

---

### 28. How do you start a service?

**Answer:**

```bash
systemctl start service_name
```

---

### 29. How do you stop a service?

**Answer:**

```bash
systemctl stop service_name
```

---

### 30. How do you check the status of a service?

**Answer:**

```bash
systemctl status service_name
```

---

### 31. What is the difference between `start` and `enable`?

**Answer:**

- `start` starts the service immediately.
- `enable` starts the service automatically during system boot.

---

### 32. How do you disable a service?

**Answer:**

```bash
systemctl disable service_name
```

---

## SOC Interview Questions

### 33. Which log file stores authentication logs in Red Hat Linux?

**Answer:**

```text
/var/log/secure
```

---

### 34. Which command is used to view systemd logs?

**Answer:**

```bash
journalctl
```

---

### 35. Where are Apache access logs stored in Red Hat?

**Answer:**

```text
/var/log/httpd/access_log
```

---

### 36. Which command is commonly used by SOC analysts to monitor logs in real time?

**Answer:**

```bash
tail -f /var/log/secure
```

or

```bash
journalctl -f
```

---

# Frequently Asked Practical Questions

- Create a directory inside another directory.
- Delete a non-empty directory.
- Display only the first five lines of a file.
- Display only the last five lines of a file.
- Find the IP address of your system.
- Check whether a server is reachable.
- Find the PID of a running process.
- Kill a running process.
- Start and stop a Linux service.
- Check the status of the firewall service.
- View authentication logs.
- Explain the difference between `kill`, `pkill`, and `killall`.

---

# Interview Tip

For a **SOC Analyst fresher interview**, be comfortable explaining:
- Directory management (`mkdir`, `rmdir`, `rm`)
- File viewing (`cat`, `head`, `tail`)
- Networking (`ip addr`, `ping`)
- Process management (`ps`, `top`, `kill`, `pgrep`)
- Service management (`systemctl`)
- Log analysis (`journalctl`, `/var/log/secure`, `/var/log/httpd/access_log`)

