# Day 13 - Linux Log Analysis for SOC Analysts

## Objective

Learn how Linux logs are used by SOC Analysts to monitor user activity, detect attacks, investigate incidents, identify privilege escalation, and troubleshoot Linux systems.

---

# Why Linux Logs are Important

Linux logs act as digital footprints of everything happening inside the operating system.

They help security teams to:

- Monitor user logins
- Detect brute-force attacks
- Track sudo usage
- Detect privilege escalation
- Investigate security incidents
- Monitor scheduled tasks
- Troubleshoot system issues

---

# Log Storage Location

Almost all Linux logs are stored inside:

```bash
/var/log
```

Navigate to the log directory:

```bash
cd /var/log
ls
```

---

# Common Linux Log Files

| Log File | Purpose |
|----------|---------|
| `/var/log/auth.log` | Authentication logs (SSH, sudo, PAM) |
| `/var/log/syslog` | General system logs |
| `/var/log/messages` | General system events (RHEL/CentOS) |
| `/var/log/dmesg` | Kernel and hardware messages |
| `/var/log/faillog` | Failed login attempts |
| `/var/log/lastlog` | Last login of every user |
| `/var/log/btmp` | Binary file storing failed login records |
| `/var/log/boot.log` | Boot-related events |
| `/var/log/cron` | Cron job execution logs |
| `/var/log/kern.log` | Kernel logs |
| `/var/log/httpd/` | Apache web server logs |
| `/var/log/nginx/` | Nginx web server logs |

---

# Understanding auth.log

Authentication logs are among the most important logs for SOC Analysts.

It records:

- SSH login attempts
- Successful logins
- Failed logins
- sudo usage
- PAM (Pluggable Authentication Module) logs

Used to detect:

- Unauthorized access
- Brute-force attacks
- Privilege escalation
- Suspicious login activity

Example log:

```text
Jan 01 10:10:22 ubuntu sshd[1234]:
Accepted password for user from 192.168.10.1
```

---

# Analyzing Sudo Usage

Sudo logs record:

- Who executed the command
- Which command was executed
- Timestamp
- Terminal information

SOC Analysts look for:

- Unauthorized sudo usage
- Privilege escalation attempts
- Suspicious administrative commands

Search sudo logs:

```bash
grep "sudo" /var/log/auth.log
```

View your sudo history:

```bash
cat ~/.bash_history | grep sudo
```

---

# Failed Login Analysis

Failed login attempts may indicate:

- Brute-force attacks
- Password guessing
- Unauthorized access attempts

Useful commands:

View failed password attempts

```bash
grep "Failed password" /var/log/auth.log
```

View faillog

```bash
faillog -a
```

View binary failed login records

```bash
lastb
```

---

# Successful Login Analysis

Show successful SSH logins

```bash
grep "Accepted" /var/log/auth.log
```

View login history

```bash
last
```

View last login of every user

```bash
lastlog
```

---

# Other Important Log Files

## Boot Log

Contains boot process information.

```bash
cat /var/log/boot.log
```

Useful for:

- Startup troubleshooting
- Detecting persistence mechanisms

---

## Kernel Log

Kernel-related events and hardware messages.

```bash
cat /var/log/kern.log
```

---

## Hardware Log

Displays hardware detection messages.

```bash
dmesg
```

or

```bash
cat /var/log/dmesg
```

---

## Cron Logs

Cron logs record scheduled task execution.

Useful for detecting:

- Malware persistence
- Unauthorized scheduled jobs
- Automated scripts

View cron logs

```bash
cat /var/log/syslog | grep CRON
```

View root cron jobs

```bash
sudo crontab -l
```

---

# Boot Performance Analysis

Analyze boot performance:

```bash
systemd-analyze blame
```

---

# SOC Investigation Commands

### View last 50 authentication logs

```bash
tail -n 50 /var/log/auth.log
```

### Show sudo activities

```bash
grep "sudo" /var/log/auth.log
```

### Show failed password attempts

```bash
grep "Failed password" /var/log/auth.log
```

### Show successful SSH logins

```bash
grep "Accepted" /var/log/auth.log
```

### Display failed login records

```bash
faillog -a
```

### Show login history

```bash
last
```

### Show last login for each user

```bash
lastlog
```

### View boot log

```bash
cat /var/log/boot.log
```

### Analyze boot performance

```bash
systemd-analyze blame
```

### View cron execution logs

```bash
cat /var/log/syslog | grep CRON
```

### Show root cron jobs

```bash
sudo crontab -l
```

---

# SOC Analyst Use Cases

- Detect brute-force attacks
- Investigate SSH login attempts
- Monitor sudo usage
- Identify privilege escalation
- Analyze boot events
- Detect malware persistence
- Investigate scheduled tasks
- Review user login history
- Troubleshoot Linux systems

---

# Assignment

1. Login to a Linux VM.
2. Check successful and failed login attempts.
3. Review sudo usage from the last 24 hours.
4. Investigate cron job activity.
5. Analyze boot logs.
6. Identify any suspicious login or privilege escalation activity.

