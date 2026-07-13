# Day 08 - Linux File Management, Process Management & System Services (Red Hat Linux)

## Objective

Learn essential Linux commands for file management, directory operations, networking, process management, service management, and log analysis. These commands are widely used by SOC Analysts for system monitoring, troubleshooting, and incident investigation.

---

# 1. Directory Management

## Create a Directory

```bash
mkdir SOC
```

Creates a new directory named `SOC`.

### Create Directory Inside Another Directory

### Method 1

```bash
mkdir SOC
cd SOC
mkdir L1
```

### Method 2

```bash
mkdir -p SOC/L1
```

The `-p` option creates parent directories automatically if they do not exist.

---

## Remove Empty Directories

```bash
rmdir -p SOC/L1
```

Removes both `L1` and `SOC` if they are empty.

---

## Remove Directory with Files

```bash
rm -rf SOC
```

- `-r` → Recursive deletion
- `-f` → Force deletion without confirmation


---

# 2. File Reading Commands

## Display Entire File

```bash
cat filename
```

Example:

```bash
cat notes.txt
```

---

## Display First 10 Lines

```bash
head filename
```

Example:

```bash
head notes.txt
```

---

## Display Last 10 Lines

```bash
tail filename
```

Example:

```bash
tail notes.txt
```

---

## Display First 5 Lines

```bash
head -5 filename
```

---

## Display Last 5 Lines

```bash
tail -5 filename
```

---

## Merge Two Files (Concatenate)

```bash
cat file1 file2 >> file3
```

Copies the contents of `file1` and `file2` into `file3`.

---

# 3. Linux Manual

## View Manual Page

```bash
man command
```

Example:

```bash
man mkdir
```

The `man` command provides detailed information about any Linux command.

---

# 4. File System Paths

## Absolute Path

Starts from the root directory (`/`).

Example:

```text
/usr/share
```

---

## Relative Path

Starts from the current working directory.

Example:

```text
Documents/Linux
```

---

# 5. Networking Commands

## Display Network Configuration (Older Command)

```bash
ifconfig
```

Shows network interfaces, IP addresses, subnet masks, and MAC addresses.

---

## Display IP Address (Recommended)

```bash
ip addr
```

or

```bash
ip a
```

Shows all network interfaces and their IP addresses.

---

## Check Network Connectivity

```bash
ping google.com
```

Used to test whether a host is reachable over the network.

---

# 6. Process Management

## Show Running Processes

```bash
ps
```

Displays currently running processes.

---

## Display All Running Processes

```bash
ps aux
```

Shows detailed information about all running processes.

---

## Real-Time Process Monitor

```bash
top
```

Displays CPU, memory usage, and running processes in real time.

---

## Find Process ID by Name

```bash
pgrep firefox
```

Returns the Process ID (PID) of the specified process.

---

## Find PID

```bash
pidof firefox
```

Returns the PID of a running process.

---

## Kill a Process

```bash
kill PID
```

Example:

```bash
kill 1234
```

---

## Force Kill a Process

```bash
kill -9 PID
```

Forcefully terminates the specified process.

---

## List All Kill Signals

```bash
kill -l
```

Displays all available kill signals.

---

## Kill Process by Name

```bash
pkill firefox
```

Kills a process using its name.

---

## Kill All Processes with Same Name

```bash
killall firefox
```

Terminates all processes matching the specified name.

---

# 7. Service Management

Linux services are managed using `systemctl`.

## Start Service

```bash
systemctl start service_name
```

Example:

```bash
systemctl start firewalld
```

---

## Stop Service

```bash
systemctl stop service_name
```

---

## Check Service Status

```bash
systemctl status service_name
```

---

## Enable Service at Boot

```bash
systemctl enable service_name
```

---

## Disable Service

```bash
systemctl disable service_name
```

---

# 8. Firewall Management

## Check Firewall Status

```bash
sudo systemctl status firewalld
```

---

## Start Firewall Service

```bash
sudo systemctl start firewalld
```

---

## Enable Firewall at Boot

```bash
sudo systemctl enable firewalld
```

---

# 9. Important Linux Log Files (SOC Perspective)

## Authentication Logs (RHEL)

```text
/var/log/secure
```

Contains login attempts, authentication events, and SSH activity.

---

## System Logs

```text
/var/log/messages
```

Stores general system messages and events.

---

## Apache Access Logs

```text
/var/log/httpd/access_log
```

Contains records of web server requests.

---

## Apache Error Logs

```text
/var/log/httpd/error_log
```

Contains web server error messages.

---

## Systemd Logs

```bash
journalctl
```

Displays system and service logs managed by systemd.

---

