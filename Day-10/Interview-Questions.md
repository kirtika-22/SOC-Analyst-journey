# Day 10 - Interview Questions (Windows Internals for SOC Analysts)

## Basic Interview Questions

### 1. What are the two execution modes in Windows?
**Answer:**
- User Mode
- Kernel Mode

---

### 2. What is User Mode?
**Answer:**
User Mode is where normal applications run with limited privileges. Applications cannot directly access hardware and must request services from the operating system.

---

### 3. What is Kernel Mode?
**Answer:**
Kernel Mode is the privileged mode of Windows where the operating system has unrestricted access to hardware, memory, and system resources.

---

### 4. What is the responsibility of the Windows Kernel?
**Answer:**
The Windows Kernel manages:
- Memory
- Processes
- Threads
- Device Drivers
- CPU Scheduling
- Security

---

### 5. What is HAL (Hardware Abstraction Layer)?
**Answer:**
HAL acts as a bridge between Windows and the physical hardware, allowing Windows to work with different hardware platforms.

---

### 6. What is NTOSKRNL.EXE?
**Answer:**
NTOSKRNL.EXE is the core Windows kernel responsible for memory management, process scheduling, security, and hardware communication.

---

### 7. What is the Win32 Subsystem?
**Answer:**
The Win32 Subsystem provides the Windows graphical interface (GUI), console applications, and Windows API support.

---

## Windows Processes

### 8. What is wininit.exe?
**Answer:**
It initializes Windows services during the system startup process.

---

### 9. What is csrss.exe?
**Answer:**
CSRSS (Client/Server Runtime Subsystem) manages console windows, user sessions, and thread creation.

---

### 10. What is svchost.exe?
**Answer:**
svchost.exe is a Service Host process that runs one or more Windows services.

---

### 11. Is it normal to see multiple svchost.exe processes?
**Answer:**
Yes. Windows groups services into multiple svchost.exe processes for stability and security.

---

## Windows Directories

### 12. What is stored inside C:\Windows\System32?
**Answer:**
It contains important Windows executables, DLLs, drivers, and system utilities.

---

### 13. Why is System32 important for SOC Analysts?
**Answer:**
Malware often targets System32 for DLL injection, persistence, and replacing legitimate files.

---

### 14. What is the purpose of the C:\Users directory?
**Answer:**
It stores user profiles such as Desktop, Documents, Downloads, and AppData.

---

### 15. Why do attackers often use the AppData folder?
**Answer:**
Because users have write permissions there, making it a common location to hide malware and persistence files.

---

### 16. What is the difference between Program Files and Program Files (x86)?
**Answer:**
- Program Files → 64-bit applications
- Program Files (x86) → 32-bit applications

---

## Windows Utilities

### 17. How do you open Task Manager?
**Answer:**
**Ctrl + Shift + Esc**

---

### 18. Why do SOC Analysts use Task Manager?
**Answer:**
To identify:
- High CPU usage
- High memory usage
- Suspicious processes
- Startup applications

---

### 19. What is Event Viewer?
**Answer:**
Event Viewer is a Windows utility used to view system, security, and application logs.

---

### 20. Which command opens Event Viewer?
**Answer:**
```cmd
eventvwr.msc
```

---

### 21. What is Registry Editor?
**Answer:**
Registry Editor is used to view and modify Windows Registry settings.

---

### 22. Which command opens Registry Editor?
**Answer:**
```cmd
regedit
```

---

### 23. What is Services Manager?
**Answer:**
It allows administrators to view, start, stop, and manage Windows services.

---

### 24. Which command opens Services Manager?
**Answer:**
```cmd
services.msc
```

---

## Windows Event Logs

### 25. Name the three important Windows Event Log categories.
**Answer:**
- Application
- System
- Security

---

### 26. Which Event Log is most important for SOC Analysts?
**Answer:**
The **Security Log**, because it records authentication, account management, and privilege events.

---

### 27. What does Event ID 4624 indicate?
**Answer:**
Successful logon.

---

### 28. What does Event ID 4625 indicate?
**Answer:**
Failed logon attempt.

---

### 29. What does Event ID 4688 indicate?
**Answer:**
A new process has been created.

---

### 30. Why is Event ID 1102 considered suspicious?
**Answer:**
It indicates that the Windows Security Log has been cleared, which may be an attempt to hide malicious activity.

---

### 31. What does Event ID 4720 indicate?
**Answer:**
A new user account has been created.

---

### 32. What does Event ID 4726 indicate?
**Answer:**
A user account has been deleted.

---

## Windows Commands

### 33. What does ipconfig do?
**Answer:**
Displays IP address and network configuration.

---

### 34. What does netstat -ano display?
**Answer:**
Active network connections, listening ports, and associated Process IDs (PIDs).

---

### 35. What does tasklist do?
**Answer:**
Lists all currently running processes.

---

### 36. What is taskkill used for?
**Answer:**
Terminates a running process using its PID.

---

### 37. What does whoami display?
**Answer:**
The currently logged-in user.

---

### 38. What information does systeminfo provide?
**Answer:**
Operating system version, installed updates, hardware details, and patch level.

---

### 39. What is WMIC?
**Answer:**
WMIC (Windows Management Instrumentation Command-line) is used to retrieve system and process information.

---

### 40. Why is PowerShell important in cybersecurity?
**Answer:**
It is used for automation, administration, scripting, threat hunting, and incident response.

---

## Persistence

### 41. What is Startup Folder Abuse?
**Answer:**
Attackers place malicious executables or scripts in the Startup folder so they run automatically after user login.

---

### 42. What is the Registry Run Key?
**Answer:**
A registry location where programs are configured to start automatically during user logon.

Example:
```
HKCU\Software\Microsoft\Windows\CurrentVersion\Run
```

---

## SOC Investigation Tools

### 43. What is Sysinternals Suite?
**Answer:**
A collection of Microsoft tools used for troubleshooting, system monitoring, and forensic analysis.

---

### 44. What is Process Explorer?
**Answer:**
An advanced Task Manager used to inspect running processes, parent-child relationships, and loaded DLLs.

---

### 45. What is Autoruns used for?
**Answer:**
It displays all auto-start locations and helps detect persistence mechanisms.

---

### 46. What is TCPView?
**Answer:**
A tool that shows active TCP/UDP connections and listening ports.

---

### 47. What is Reliability Monitor?
**Answer:**
A Windows utility that tracks system stability, application crashes, and update history.

---

### 48. What is Process Hacker?
**Answer:**
An advanced process analysis tool used to inspect processes, services, memory, and handles.

---

## Scenario-Based Questions

### 49. A user reports that the system is very slow. What would you check first?
**Answer:**
- Task Manager
- Running processes
- CPU usage
- Memory usage
- Startup applications

---

### 50. Which Event IDs would you investigate after a suspected brute-force attack?
**Answer:**
- 4625 (Failed Logon)
- 4624 (Successful Logon)
- 4672 (Special Privileges Assigned)

---

### 51. Where would you check if you suspect malware persistence?
**Answer:**
- Startup Folder
- Registry Run Keys
- Services
- Scheduled Tasks
- AppData
- Autoruns

---

### 52. Why should every SOC Analyst understand Windows Internals?
**Answer:**
Because most enterprise environments use Windows. Understanding Windows internals helps detect malware, investigate incidents, analyze logs, identify persistence mechanisms, and perform effective threat hunting.