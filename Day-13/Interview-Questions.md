# Day 13 - Linux Log Analysis Interview Questions & Answers

# 1. What are Linux logs?

**Answer:**

Linux logs are files that record events and activities occurring on a Linux system. They help administrators and SOC Analysts monitor system health, troubleshoot issues, and investigate security incidents.

---

# 2. Where are Linux logs stored?

**Answer:**

Most Linux logs are stored in the following directory:

```bash
/var/log
```

---

# 3. Why are Linux logs important for a SOC Analyst?

**Answer:**

Linux logs help SOC Analysts:

- Detect brute-force attacks
- Monitor SSH logins
- Track sudo usage
- Detect privilege escalation
- Investigate security incidents
- Identify malware persistence
- Troubleshoot system problems

---

# 4. Which log file stores authentication events?

**Answer:**

Authentication logs are stored in:

```bash
/var/log/auth.log
```

(RHEL/CentOS may use `/var/log/secure`.)

It records:

- SSH logins
- Failed logins
- sudo activity
- PAM authentication

---

# 5. What information is stored in auth.log?

**Answer:**

`auth.log` contains:

- Successful SSH logins
- Failed SSH logins
- Sudo commands
- User authentication
- PAM authentication logs

---

# 6. Which command shows the latest authentication logs?

**Answer:**

```bash
tail -n 50 /var/log/auth.log
```

---

# 7. How do you check successful SSH logins?

**Answer:**

```bash
grep "Accepted" /var/log/auth.log
```

This displays all successful SSH login attempts.

---

# 8. How do you check failed login attempts?

**Answer:**

```bash
grep "Failed password" /var/log/auth.log
```

or

```bash
faillog -a
```

---

# 9. What is a brute-force attack?

**Answer:**

A brute-force attack is when an attacker repeatedly tries different usernames and passwords until the correct credentials are found.

SOC Analysts detect this by monitoring repeated failed login attempts in authentication logs.

---

# 10. What is sudo?

**Answer:**

`sudo` allows a permitted user to execute commands with elevated (root) privileges without logging in directly as the root user.

---

# 11. Why do SOC Analysts monitor sudo usage?

**Answer:**

SOC Analysts monitor sudo activity to detect:

- Unauthorized privilege escalation
- Misuse of administrator privileges
- Suspicious administrative commands
- Insider threats

---

# 12. Which command shows sudo activities?

**Answer:**

```bash
grep "sudo" /var/log/auth.log
```

---

# 13. Which log file records failed login attempts?

**Answer:**

```text
/var/log/faillog
```

Binary login records are stored in:

```text
/var/log/btmp
```

---

# 14. What is lastlog?

**Answer:**

`lastlog` displays the most recent login time for every user on the system.

Command:

```bash
lastlog
```

---

# 15. What is the difference between last and lastlog?

**Answer:**

| last | lastlog |
|------|----------|
| Shows complete login history | Shows only the latest login of each user |
| Uses wtmp file | Uses lastlog database |

---

# 16. Which command displays login history?

**Answer:**

```bash
last
```

---

# 17. What does the dmesg command do?

**Answer:**

`dmesg` displays kernel and hardware-related messages generated during system boot and hardware events.

---

# 18. What is boot.log?

**Answer:**

`boot.log` records events that occur during the Linux boot process.

It helps troubleshoot startup failures and detect persistence mechanisms.

---

# 19. What is kern.log?

**Answer:**

`kern.log` stores kernel-related events such as:

- Driver errors
- Hardware issues
- Kernel messages
- System crashes

---

# 20. What is a cron job?

**Answer:**

A cron job is a scheduled task that automatically runs commands or scripts at specified times.

Attackers may abuse cron jobs to maintain persistence on a compromised system.

---

# 21. Which log file stores cron activity?

**Answer:**

```text
/var/log/cron
```

or

```text
/var/log/syslog
```

Search using:

```bash
grep CRON /var/log/syslog
```

---

# 22. How do you list root user's cron jobs?

**Answer:**

```bash
sudo crontab -l
```

---

# 23. What is privilege escalation?

**Answer:**

Privilege escalation is the process of gaining higher access rights than originally assigned, such as a normal user obtaining root privileges.

---

# 24. How can Linux logs help detect privilege escalation?

**Answer:**

Linux logs record:

- Sudo usage
- Authentication attempts
- User switching
- Administrative commands

These logs help identify unauthorized privilege escalation.

---

# 25. Which Linux logs are most important for SOC investigations?

**Answer:**

- `/var/log/auth.log`
- `/var/log/syslog`
- `/var/log/messages`
- `/var/log/faillog`
- `/var/log/btmp`
- `/var/log/lastlog`
- `/var/log/boot.log`
- `/var/log/kern.log`
- `/var/log/cron`

---

# 26. What is PAM?

**Answer:**

PAM (Pluggable Authentication Modules) is a framework that manages user authentication in Linux.

It provides authentication services for applications like SSH, login, and sudo.

---

# 27. Which command shows the last 50 authentication log entries?

**Answer:**

```bash
tail -n 50 /var/log/auth.log
```

---

# 28. What indicators in Linux logs may suggest an attack?

**Answer:**

- Multiple failed logins
- Repeated SSH attempts
- Unauthorized sudo usage
- Unknown cron jobs
- Unusual login times
- Privilege escalation attempts
- Unexpected service starts

---

# 29. What is persistence in cybersecurity?

**Answer:**

Persistence is a technique used by attackers to maintain access to a compromised system after reboot or user logout.

Common persistence methods include cron jobs, startup scripts, and system services.

---

# 30. Explain a basic Linux log investigation process.

**Answer:**

1. Check authentication logs (`auth.log`).
2. Review successful and failed logins.
3. Analyze sudo activity.
4. Review login history (`last`, `lastlog`).
5. Check boot logs (`boot.log`).
6. Inspect cron jobs and scheduled tasks.
7. Investigate kernel and system logs.
8. Correlate timestamps to identify suspicious activity.