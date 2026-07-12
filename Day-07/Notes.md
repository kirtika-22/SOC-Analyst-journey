# Day 7 - Linux File System, User Management & Permissions

## Linux

Linux is an open-source operating system widely used in servers, cloud computing, cybersecurity, and enterprise environments.

### Common Linux Distributions

- Ubuntu
- Kali Linux
- Debian
- Red Hat

---

# Why Linux for SOC?

- Log Analysis
- Threat Hunting
- Malware Analysis
- SIEM Tools
- IDS/IPS Support

---

# Linux File System

| Directory | Purpose |
|-----------|---------|
| / | Root Directory |
| /home | User Home Directories |
| /etc | Configuration Files |
| /var/log | System Logs |
| /bin | Essential Commands |
| /sbin | System Binaries |
| /tmp | Temporary Files |

---

# Important Log Files

- /var/log/auth.log → Authentication events
- /var/log/syslog → System logs
- /var/log/apache2/access.log → Web server access
- journalctl → Systemd logs

---

# Relative vs Absolute Path

## Absolute Path

Starts from the root directory (/).

Example

/home/kirti/Desktop/file.txt

## Relative Path

Starts from the current directory.

Example

Desktop/file.txt

---

# Basic Linux Commands

pwd → Show current directory

whoami → Display logged-in user

ls → List files

ll → Long listing

ls -lt → Sort by latest modified

ls -ltr → Sort oldest first

touch file.txt → Create file

mkdir folder → Create folder

rmdir folder → Remove empty folder

rm file.txt → Delete file

cat file.txt → Display file content

gedit file.txt → Edit file (GUI)

vim file.txt → Edit file (Terminal)

mv old new → Rename or move file

cd folder → Change directory

cd .. → Go one directory back

---

# Multiple File Creation

touch file{1..10}

mkdir folder{1..10}

---

# User Management

Create User

sudo useradd username

Check User

id username

Delete User

sudo userdel username

Set Password

sudo passwd username

Switch User

su username

Run Command as Root

sudo command

---

# File Permissions

Permissions consist of:

Owner (User)

Group

Others

Permission Types

r = Read (4)

w = Write (2)

x = Execute (1)

Examples

777 → rwxrwxrwx

755 → rwxr-xr-x

644 → rw-r--r--

Change Permissions

chmod 777 filename

chmod u+rwx filename

chmod g+w filename

chmod o-r filename

Check Permissions

ls -l

---

# Key Learning

- Linux uses a hierarchical file system.
- Authentication logs help investigate login events.
- Users should have least privilege.
- chmod controls file access.
- Understanding Linux permissions is essential for SOC analysts.