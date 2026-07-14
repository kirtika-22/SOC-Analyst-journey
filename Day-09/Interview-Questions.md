# Day 09 - Interview Questions (Password Management, User Management & Linux Filters)

## Basic Interview Questions

### 1. What is the purpose of the `passwd` command?

**Answer:**
The `passwd` command is used to change or set a user's password in Linux.

---

### 2. What is `/etc/shadow`?

**Answer:**
`/etc/shadow` is a protected file that stores encrypted passwords and password aging information. Only the root user can read it.

---

### 3. What information is stored in `/etc/shadow`?

**Answer:**
- Encrypted password
- Password last changed date
- Minimum password age
- Maximum password age
- Password expiry date
- Warning period
- Account inactivity period

---

### 4. What is the difference between `/etc/passwd` and `/etc/shadow`?

| `/etc/passwd` | `/etc/shadow` |
|---------------|---------------|
| Stores user account information | Stores encrypted passwords |
| Readable by all users | Accessible only by root |
| Does not store actual passwords | Stores password hashes and aging information |

---

### 5. What does the `groups` command do?

**Answer:**
It displays all the groups that the current user belongs to.

---

### 6. Which file stores Linux group information?

**Answer:**
`/etc/group`

---

### 7. How do you delete a group?

**Answer:**

```bash
sudo groupdel groupname
```

---

### 8. Can you delete a user's primary group?

**Answer:**
No. A user's primary group cannot be deleted while it is assigned to that user.

---

### 9. What is the purpose of the `comm` command?

**Answer:**
It compares two **sorted** files line by line and displays unique and common lines.

---

### 10. What is the difference between `find` and `locate`?

**Answer:**

| find | locate |
|------|---------|
| Searches the filesystem | Searches an indexed database |
| Slower | Faster |
| Real-time search | Uses a prebuilt database |

---

### 11. What does the `date` command display?

**Answer:**
It displays the current date, time, and timezone.

---

### 12. What is the use of the `cal` command?

**Answer:**
It displays the calendar of the current month or a specified month/year.

---

### 13. What is the purpose of the `tar` command?

**Answer:**
It is used to archive, compress, and extract files.

---

### 14. What does the `whoami` command do?

**Answer:**
It displays the username of the currently logged-in user.

---

### 15. What is the difference between `who` and `whoami`?

| who | whoami |
|------|---------|
| Shows all logged-in users | Shows only the current user |

---

### 16. What information does the `id` command display?

**Answer:**
- User ID (UID)
- Group ID (GID)
- Supplementary Groups

---

### 17. How do you create a new user?

```bash
sudo useradd username
```

---

### 18. How do you delete a user?

```bash
sudo userdel username
```

Delete the user along with the home directory:

```bash
sudo userdel -r username
```

---

### 19. How do you lock a user account?

```bash
sudo usermod -L username
```

---

### 20. How do you unlock a user account?

```bash
sudo usermod -U username
```

---

### 21. How do you change a user's default shell?

```bash
sudo chsh -s /bin/bash username
```

---

### 22. What does the `file` command do?

**Answer:**
It identifies and displays the type of a file.

---

### 23. What does the `du` command do?

**Answer:**
It displays disk usage of files and directories.

---

### 24. What is the purpose of the `zip` command?

**Answer:**
It compresses files into a ZIP archive.

---

### 25. What does the `unzip` command do?

**Answer:**
It extracts files from a ZIP archive.

---

### 26. What does the `wc` command do?

**Answer:**
It counts lines, words, characters, and bytes in a file.

---

### 27. What is the difference between `wc -l`, `wc -m`, and `wc -c`?

| Command | Purpose |
|----------|----------|
| `wc -l` | Count lines |
| `wc -m` | Count characters |
| `wc -c` | Count bytes |

---

### 28. What is the use of the `sort` command?

**Answer:**
It sorts file contents alphabetically or numerically.

---

### 29. What does the `uniq` command do?

**Answer:**
It removes consecutive duplicate lines from a sorted file.

---

### 30. Why is `sort` commonly used before `uniq`?

**Answer:**
Because `uniq` removes only adjacent duplicate lines. Sorting places duplicate lines together.

---

### 31. What is the purpose of the `tee` command?

**Answer:**
It displays command output on the terminal while simultaneously saving it to a file.

---

### 32. What does the `grep` command do?

**Answer:**
It searches for a specific word or pattern in a file or command output.

---

### 33. Give an example of the `grep` command.

```bash
grep root /etc/passwd
```

---

### 34. What is the purpose of the `cut` command?

**Answer:**
It extracts selected columns, fields, or characters from a file or command output.

---

### 35. Give an example of the `cut` command.

```bash
echo "CyberSecurity" | cut -c1-5
```

Output:

```text
Cyber
```

---

# Scenario-Based Interview Questions

### 36. A user forgot their password. Which command would you use to reset it?

**Answer:**

```bash
sudo passwd username
```

---

### 37. Which file would you inspect to verify password expiry information?

**Answer:**
`/etc/shadow`

---

### 38. How would you check which groups a user belongs to?

**Answer:**

```bash
groups username
```

or

```bash
id username
```

---

### 39. How would you find all lines containing the word "error" in a log file?

**Answer:**

```bash
grep "error" logfile.log
```

---

### 40. How would you count the number of lines in a log file?

**Answer:**

```bash
wc -l logfile.log
```

---

### 41. How would you remove duplicate entries from a file?

**Answer:**

```bash
sort filename | uniq
```

---

### 42. How would you archive an entire directory?

**Answer:**

```bash
tar -cvf backup.tar directory/
```

---

### 43. How would you check the size of a directory?

**Answer:**

```bash
du -sh directory/
```

---

### 44. How would you quickly locate a file named `passwd`?

**Answer:**

```bash
locate passwd
```

---

### 45. Which Linux commands are most commonly used by SOC Analysts?

**Answer:**
- grep
- find
- locate
- cut
- tee
- sort
- uniq
- wc
- tar
- id
- who
- whoami
- passwd
- useradd
- userdel
- usermod
- groups

---

# Quick Revision

- `passwd` → Change password
- `/etc/shadow` → Encrypted passwords
- `groups` → Show user groups
- `groupdel` → Delete group
- `comm` → Compare sorted files
- `find` → Search files
- `locate` → Fast file search
- `date` → Display date & time
- `cal` → Calendar
- `tar` → Archive files
- `whoami` → Current user
- `who` → Logged-in users
- `id` → UID, GID, groups
- `useradd` → Create user
- `userdel` → Delete user
- `usermod` → Modify user
- `file` → File type
- `du` → Disk usage
- `zip` / `unzip` → Compress & extract
- `wc` → Count lines/words/characters
- `sort` → Sort data
- `uniq` → Remove duplicate lines
- `tee` → Display & save output
- `grep` → Search patterns
- `cut` → Extract fields/characters

---
