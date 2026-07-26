# Day 16 - Ubuntu Lab Setup & Wazuh Dashboard Installation

## Objective
Set up Ubuntu in VMware and prepare the environment for SOC monitoring by installing the Wazuh Dashboard.

---

## Lab Environment

- Host OS: Windows
- Virtual Machine: VMware Workstation
- Guest OS: Ubuntu
- Network: NAT

---

## Ubuntu Installation

### Step 1 - Create Virtual Machine
- Created a new virtual machine in VMware.
- Selected the Ubuntu ISO file.
- Allocated RAM, CPU cores, and disk space.
- Powered on the VM.

### Step 2 - Install Ubuntu
- Selected **Install Ubuntu**.
- Configured language and keyboard.
- Created a user account.
- Completed the installation and restarted the system.

---

## Update the System

```bash
sudo apt update
sudo apt upgrade -y
```

---

## Verify Internet Connection

```bash
ping google.com
```

---

## Check System Information

```bash
hostname -I
ip a
uname -a
lsb_release -a
```

---

## Basic Linux Commands Practiced

```bash
pwd
ls
cd
mkdir
touch
cp
mv
rm
history
clear
```

---

# Wazuh Dashboard Installation

Install the Wazuh Dashboard to monitor security events through a web interface.

---

## Step 1 - Update Ubuntu

```bash
sudo apt update
sudo apt upgrade -y
```

---

## Step 2 - Download the Wazuh Installation Script

```bash
curl -sO https://packages.wazuh.com/4.12/wazuh-install.sh
```

---

## Step 3 - Make the Script Executable

```bash
chmod +x wazuh-install.sh
```

---

## Step 4 - Install Wazuh

Run the all-in-one installation:

```bash
sudo bash wazuh-install.sh -a
```

This installs:
- Wazuh Manager
- Wazuh Indexer
- Wazuh Dashboard

---

## Step 5 - Verify Wazuh Services

Check the status of each service:

```bash
sudo systemctl status wazuh-manager
```

```bash
sudo systemctl status wazuh-indexer
```

```bash
sudo systemctl status wazuh-dashboard
```

---

## Step 6 - Access the Dashboard

Open your browser and navigate to:

```text
https://<Ubuntu-IP>:5601
```

Example:

```text
https://192.168.x.x:5601
```

---

## Step 7 - Log In

Use the username and password generated during the installation process to sign in to the Wazuh Dashboard.

---

## Step 8 - Verify Installation

After logging in:

- Check that the Dashboard loads successfully.
- Verify that the Wazuh Manager is connected.
- Confirm that all services are running properly.
- Ensure the system is ready for monitoring endpoints.


---

## Tools Used

- VMware Workstation
- Ubuntu
- Linux Terminal
- Wazuh Dashboard
- Splunk (Introduction)