# Day 09 - Linux Password Management, Group Management & Linux Filters

## Objective

To understand Linux password management, group management, user management, and essential Linux utilities used in system administration and SOC (Security Operations Center) operations. These commands are frequently used for user auditing, log analysis, file management, and troubleshooting Linux systems.

---

# Password Management

## What is a Password?

A password is used to authenticate a user before granting access to the Linux system.

Command to change a user's password:

```bash
passwd
```

For another user (Root):

```bash
sudo passwd username
```

---

## Shadow File

The `/etc/shadow` file stores encrypted user passwords and password aging information.

Unlike `/etc/passwd`, only the root user can read this file.

### It stores:

- Encrypted password
- Password last changed date
- Minimum password age
- Maximum password age
- Password expiry date
- Warning period before password expires
- Account inactivity period

Display the shadow file:

```bash
sudo cat /etc/shadow
```

---

# Group Management

## groups

Displays all groups that the current user belongs to.

```bash
groups
```

Example Output:

```text
student wheel docker
```

---

## View All Groups

Linux stores all group information inside:

```text
/etc/group
```

Display all groups:

```bash
cat /etc/group
```

---

## Delete a Group

```bash
sudo groupdel groupname
```

Example:

```bash
sudo groupdel developers
```

> **Note:** You cannot delete a user's primary group.

---

# comm Command

The `comm` command compares two **sorted** files line by line.

Syntax:

```bash
comm file1 file2
```

Example:

```bash
comm list1.txt list2.txt
```

---

# Basic Linux Tools

## 1. find

Searches for files and directories.

Syntax:

```bash
find <path> -name filename
```

Example:

```bash
find /home -name notes.txt
```

---

## 2. locate

Searches files using an indexed database.

Syntax:

```bash
locate filename
```

Example:

```bash
locate passwd
```

> **Note:** Much faster than `find` because it searches an index.

---

## 3. date

Displays the current:

- Date
- Time
- Timezone

Syntax:

```bash
date
```

---

## 4. cal

Displays the calendar.

Syntax:

```bash
cal
```

Displays the current month with today's date highlighted.

---

## 5. tar

Used to archive and extract files.

Create Archive

```bash
tar -cvf archive.tar folder/
```

Extract Archive

```bash
tar -xvf archive.tar
```

---

## 6. whoami

Displays the currently logged-in username.

```bash
whoami
```

Example Output:

```text
student
```

---

## 7. who

Displays users currently logged into the system.

```bash
who
```

---

## 8. id

Displays:

- User ID (UID)
- Group ID (GID)
- Supplementary Groups

```bash
id
```

Example Output:

```text
uid=1000(student)
gid=1000(student)
groups=1000(student),10(wheel)
```

---

# User Management

## Add User

```bash
useradd username
```

Example:

```bash
sudo useradd john
```

---

## Delete User

```bash
userdel username
```

Delete user along with home directory:

```bash
userdel -r username
```

---

## Modify User

```bash
usermod options username
```

---

## Lock User Account

```bash
usermod -L username
```

---

## Unlock User Account

```bash
usermod -U username
```

---

## Change Login Shell

```bash
chsh -s /bin/bash username
```

---

# File Utility Commands

## file

Displays the type of a file.

Syntax:

```bash
file filename
```

Example:

```bash
file report.pdf
```

---

## du

Displays disk usage.

Syntax:

```bash
du -sh foldername
```

Example:

```bash
du -sh Downloads
```

---

## zip

Compress files.

```bash
zip archive.zip file.txt
```

---

## unzip

Extract ZIP archives.

```bash
unzip archive.zip
```

---

# Text Processing Commands

## wc

Counts:

- Lines
- Words
- Characters
- Bytes

Syntax:

```bash
wc filename
```

Examples:

Count Lines

```bash
wc -l filename
```

Count Characters

```bash
wc -m filename
```

Count Bytes

```bash
wc -c filename
```

---

## sort

Sorts file contents alphabetically.

Syntax:

```bash
sort filename
```

or

```bash
cat filename | sort
```

---

## uniq

Removes consecutive duplicate lines.

Syntax:

```bash
uniq filename
```

Usually combined with sort:

```bash
sort filename | uniq
```

---

# Linux Filters

Linux filters process text received from standard input and produce filtered output.

---

## tee

Displays output on the terminal and saves it to a file simultaneously.

Syntax:

```bash
cat /etc/passwd | tee newfile.txt
```

---

## grep

Searches for a specific word or pattern inside a file.

Syntax:

```bash
grep "word" filename
```

Example:

```bash
grep root /etc/passwd
```

or

```bash
cat filename | grep admin
```

---

## cut

Extracts selected characters or fields from each line.

Display first five characters:

```bash
echo "CyberSecurity" | cut -c1-5
```

Output

```text
Cyber
```

Extract fields:

```bash
cut -d":" -f1 /etc/passwd
```

---

# Important Configuration Files

| File | Purpose |
|------|----------|
| `/etc/passwd` | User account information |
| `/etc/shadow` | Encrypted passwords and password aging |
| `/etc/group` | Group information |

---


# Key Takeaways

- `/etc/shadow` securely stores encrypted passwords and password aging information.
- Groups help manage permissions efficiently.
- `find` searches the filesystem, while `locate` searches an indexed database.
- `tar`, `zip`, and `unzip` are used for archiving and compression.
- `grep`, `cut`, `tee`, `sort`, `uniq`, and `wc` are powerful Linux text-processing commands.
- User management commands are essential for Linux administration.
- These commands are widely used in SOC operations for log analysis, user auditing, and system troubleshooting.

---