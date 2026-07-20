# Day 12 - Windows Event Logs Deep Dive (Interview Questions)

## 1. What are Windows Event Logs?

**Answer:**
Windows Event Logs are built-in logs that record security, system, and application activities on a Windows machine. They help administrators and SOC analysts monitor user activity, troubleshoot issues, detect attacks, and investigate security incidents.

---

## 2. What are the three main types of Windows logs?

**Answer:**
- Security Logs
- System Logs
- Application Logs

---

## 3. Why are Windows Security Logs important for SOC analysts?

**Answer:**
Security logs record authentication, authorization, account management, privilege changes, and security-related events. They help detect brute-force attacks, privilege escalation, lateral movement, insider threats, and compromised accounts.

---

## 4. What is Event ID 4624?

**Answer:**
Event ID 4624 indicates a successful user logon. It is used to verify legitimate logins, monitor user activity, and detect suspicious login locations or times.

---

## 5. What is Event ID 4625?

**Answer:**
Event ID 4625 records a failed logon attempt. Multiple failed logins may indicate brute-force attacks, password spraying, or credential stuffing.

---

## 6. What is Event ID 4648?

**Answer:**
Event ID 4648 is generated when a logon uses explicit credentials. It can indicate lateral movement or administrative activities using alternate credentials.

---

## 7. What is Event ID 4672?

**Answer:**
Event ID 4672 indicates that special privileges were assigned to a new logon. It usually appears when an administrator logs in and is useful for detecting privilege escalation.

---

## 8. What is Event ID 4688?

**Answer:**
Event ID 4688 indicates that a new process has been created. It is one of the most important events for detecting malware, ransomware, PowerShell attacks, and suspicious command execution.

---

## 9. What is Event ID 4689?

**Answer:**
Event ID 4689 records that a process has ended. SOC analysts monitor it to identify unexpected termination of antivirus or security-related processes.

---

## 10. What is Event ID 4698?

**Answer:**
Event ID 4698 indicates that a scheduled task has been created. Attackers often use scheduled tasks to maintain persistence.

---

## 11. What is Event ID 4703?

**Answer:**
Event ID 4703 records changes to user rights or privileges. It helps detect privilege escalation.

---

## 12. What is Event ID 4720?

**Answer:**
Event ID 4720 indicates that a new user account has been created.

---

## 13. What is Event ID 4726?

**Answer:**
Event ID 4726 indicates that a user account has been deleted.

---

## 14. What is Event ID 4732?

**Answer:**
Event ID 4732 indicates that a user has been added to a local security group, which may increase privileges.

---

## 15. What is Event ID 4738?

**Answer:**
Event ID 4738 indicates that a user account has been modified.

---

## 16. What is Event ID 4740?

**Answer:**
Event ID 4740 indicates that a user account has been locked out, often due to repeated failed login attempts.

---

## 17. What is Event ID 4743?

**Answer:**
Event ID 4743 indicates that a computer account has been deleted from Active Directory.

---

## 18. What is Event ID 4756?

**Answer:**
Event ID 4756 indicates that a user has been added to a universal security group.

---

## 19. What is Event ID 4768?

**Answer:**
Event ID 4768 records a Kerberos Ticket Granting Ticket (TGT) request during user authentication.

---

## 20. What is Event ID 4769?

**Answer:**
Event ID 4769 records a Kerberos Service Ticket request and is commonly monitored to detect Kerberoasting attacks.

---

## 21. What is Event ID 4776?

**Answer:**
Event ID 4776 records NTLM authentication validation requests.

---

## 22. What is Event ID 4798?

**Answer:**
Event ID 4798 records when a user's group memberships are queried. It may indicate attacker reconnaissance.

---

## 23. What is Event ID 5058?

**Answer:**
Event ID 5058 records cryptographic key operations performed by Windows.

---

## 24. What is Event ID 5140?

**Answer:**
Event ID 5140 indicates that a shared network resource has been accessed.

---

## 25. What is Event ID 5152?

**Answer:**
Event ID 5152 indicates that Windows Filtering Platform blocked a network packet.

---

## 26. What is Event ID 5156?

**Answer:**
Event ID 5156 indicates that Windows Firewall allowed a network connection.

---

## 27. What is Event ID 1102?

**Answer:**
Event ID 1102 indicates that the Windows Security Audit Log has been cleared. This is a high-priority event because attackers often clear logs to hide their activities.

---

## 28. What are Windows Logon Types?

**Answer:**

| Logon Type | Description |
|------------|-------------|
| 2 | Interactive Logon |
| 3 | Network Logon |
| 5 | Service Logon |
| 7 | Unlock Workstation |
| 10 | Remote Interactive (RDP) |

---

## 29. What is Logon Type 2?

**Answer:**
A user logs in directly using the keyboard and monitor.

---

## 30. What is Logon Type 3?

**Answer:**
A user accesses the system over the network, such as SMB or a shared folder.

---

## 31. What is Logon Type 5?

**Answer:**
Used when a Windows service starts using a service account.

---

## 32. What is Logon Type 7?

**Answer:**
Generated when a user unlocks a previously locked workstation.

---

## 33. What is Logon Type 10?

**Answer:**
Generated during Remote Desktop Protocol (RDP) logins.

---

## 34. What is Event ID 1149?

**Answer:**
Event ID 1149 indicates successful Remote Desktop authentication.

---

## 35. Which Event IDs are commonly used for RDP investigations?

**Answer:**
- 1149 – Successful RDP authentication
- 4624 – Successful RDP logon
- 21 – Session logon
- 22 – Shell start
- 23 – Session logoff
- 1024 – RDP operational event

---

## 36. Which Event ID is most useful for detecting malware execution?

**Answer:**
Event ID **4688** because it records newly created processes.

---

## 37. Which Event ID helps detect brute-force attacks?

**Answer:**
Event ID **4625** because it records failed logon attempts.

---

## 38. Which Event ID helps detect privilege escalation?

**Answer:**
Event IDs **4672, 4703, 4732, and 4756**.

---

## 39. Which Event ID is most suspicious if an attacker wants to hide their actions?

**Answer:**
Event ID **1102**, because it indicates the audit log has been cleared.

---

## 40. What should a SOC analyst check while investigating Windows Event Logs?

**Answer:**
- Username
- Source IP Address
- Destination Host
- Logon Type
- Timestamp
- Process Name
- Parent Process
- Command Line
- Event ID
- Privileges
- Authentication Method
- Related Events

---

## 41. What is the biggest mistake beginners make while investigating logs?

**Answer:**
Investigating a single Event ID without correlating related events. SOC analysts should always build a timeline using multiple Event IDs.

---

## 42. Which Windows Event IDs are considered must-know for SOC Analyst interviews?

**Answer:**
4624, 4625, 4648, 4672, 4688, 4689, 4698, 4703, 4720, 4726, 4732, 4738, 4740, 4743, 4756, 4768, 4769, 4776, 4798, 5058, 5140, 5152, 5156, and 1102.