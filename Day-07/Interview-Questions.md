# Day 7 - Interview Questions & Answers (Linux File System, User Management & Permissions)

## 1. What is Linux?

Linux is an open-source operating system based on Unix. It is widely used in servers, cloud computing, cybersecurity, and enterprise environments.

---

## 2. Why is Linux important for SOC Analysts?

- Most servers run Linux.
- Security logs are stored in Linux.
- SOC analysts investigate incidents using Linux commands.
- Many security tools run on Linux.

---

## 3. Name some popular Linux distributions.

- Ubuntu
- Debian
- Kali Linux
- Red Hat Enterprise Linux (RHEL)
- CentOS

---

## 4. What is the root directory?

The root directory (/) is the top-level directory of the Linux file system. Every file and folder starts from it.

---

## 5. What is the purpose of the /home directory?

It stores personal files and folders of users.

Example:
```
/home/kirtika
```

---

## 6. What is stored in /etc?

Configuration files of the operating system and applications.

---

## 7. What is the purpose of /var/log?

It stores system and application log files.

---

## 8. What is the use of /var/log/auth.log?

It stores authentication events such as:

- Login attempts
- SSH logins
- sudo usage
- Failed logins

---

## 9. What is /var/log/syslog?

It stores general system logs and service messages.

---

## 10. What is journalctl?

`journalctl` displays logs collected by systemd.

Example:
```
journalctl
```

---

## 11. What does the pwd command do?

Displays the current working directory.

Example:
```
pwd
```

---

## 12. What does whoami do?

Displays the currently logged-in user.

Example:
```
whoami
```

---

## 13. Difference between ls and ll?

- `ls` → Lists files and directories.
- `ll` → Shows detailed information such as permissions, owner, size, and date.

---

## 14. What is the difference between ls -lt and ls -ltr?

- `ls -lt` → Newest files first.
- `ls -ltr` → Oldest files first.

---

## 15. What does touch do?

Creates an empty file.

Example:
```
touch notes.txt
```

---

## 16. What does mkdir do?

Creates a new directory.

Example:
```
mkdir Projects
```

---

## 17. Difference between rm and rmdir?

- `rm` removes files.
- `rmdir` removes empty directories.

---

## 18. What does cat do?

Displays the contents of a file.

Example:
```
cat notes.txt
```

---

## 19. Difference between gedit and vim?

- `gedit` is a graphical text editor.
- `vim` is a terminal-based text editor.

---

## 20. What does mv do?

Moves or renames files.

Example:
```
mv old.txt new.txt
```

---

## 21. What is an Absolute Path?

The complete path starting from the root directory (/).

Example:
```
/home/kirtika/Documents/file.txt
```

---

## 22. What is a Relative Path?

A path relative to the current working directory.

Example:
```
Documents/file.txt
```

---

## 23. Difference between Absolute Path and Relative Path?

| Absolute Path | Relative Path |
|---------------|---------------|
| Starts with / | Does not start with / |
| Complete path | Depends on current directory |

---

## 24. How do you create a new user?

```
sudo useradd username
```

---

## 25. How do you delete a user?

```
sudo userdel username
```

---

## 26. How do you assign a password to a user?

```
sudo passwd username
```

---

## 27. What does the id command do?

Displays the user's UID, GID, and groups.

Example:
```
id username
```

---

## 28. What is the su command?

Switches from one user to another.

Example:
```
su username
```

---

## 29. What is sudo?

Runs a command with administrator (root) privileges.

Example:
```
sudo apt update
```

---

## 30. What are Linux file permissions?

Permissions determine who can read, write, or execute a file.

There are three permission groups:

- User (Owner)
- Group
- Others

---

## 31. What do r, w, and x mean?

- r = Read (4)
- w = Write (2)
- x = Execute (1)

---

## 32. What does chmod do?

Changes file permissions.

Example:
```
chmod 755 file.txt
```

---

## 33. What does chmod 777 mean?

Everyone (owner, group, others) gets:

- Read
- Write
- Execute

It is **not recommended** for sensitive files because it is insecure.

---

## 34. What does chmod 644 mean?

- Owner → Read & Write
- Group → Read
- Others → Read

Commonly used for normal files.

---

## 35. How do you check file permissions?

```
ls -l
```

---

# HR Style Questions

### Why should a SOC Analyst know Linux?

Because most enterprise servers run Linux, and security investigations require log analysis, file management, user management, and permission checking.

---

### Which Linux command do you use the most?

"I frequently use pwd, ls, cd, cat, touch, mkdir, rm, chmod, journalctl, and whoami for navigation, file management, and log analysis."

---

### Which Linux topic is most important for SOC?

- Log analysis
- File permissions
- User management
- Authentication logs
- System logs