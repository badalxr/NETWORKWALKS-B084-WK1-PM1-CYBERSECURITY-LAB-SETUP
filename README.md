<div align="center">🔐 Cybersecurity Lab Environment Setup

Building an isolated virtual lab for penetration testing and ethical hacking practice

</div><p align="center">
  <img src="https://img.shields.io/badge/Skill-Cybersecurity-404040?style=flat-square&labelColor=C00000" />
  <img src="https://img.shields.io/badge/VirtualBox-7.2-0070C0?style=flat-square&logo=virtualbox&logoColor=white" />
  <img src="https://img.shields.io/badge/Kali%20Linux-2026.2-E87500?style=flat-square&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/Network-10.0.0.0%2F24-238F89?style=flat-square" />
  <img src="https://img.shields.io/badge/Penetration%20Testing-Ethical%20Hacking-C00000?style=flat-square" />
  <img src="https://img.shields.io/badge/Linux-Administration-404040?style=flat-square&logo=linux" />
  <img src="https://img.shields.io/badge/Networkwalks-Batch%20B084-C00000?style=flat-square" />
</p>---

📌 Project Overview

This project focuses on building a virtual cybersecurity and penetration-testing laboratory using Oracle VirtualBox and Kali Linux.

The main objective is to create a controlled virtual environment where cybersecurity tools, network scanning, reconnaissance, vulnerability assessment, and other security-testing activities can be performed safely.

The laboratory uses a private NAT Network, allowing multiple virtual machines to communicate with each other while maintaining external network connectivity.

---

🎯 Project Objectives

- Install and configure Oracle VirtualBox.
- Import and configure Kali Linux.
- Create a private NAT Network.
- Configure Kali Linux network settings.
- Assign a consistent IPv4 address to Kali Linux.
- Verify network connectivity and DNS resolution.
- Understand NAT vs NAT Network.
- Create a clean VM snapshot for recovery.
- Document the complete laboratory setup.

---

🛡️ Purpose of the Lab

This laboratory provides a safe and controlled environment for learning cybersecurity and ethical hacking.

It can be used for:

- Network Reconnaissance
- Port Scanning
- Vulnerability Assessment
- Packet Analysis
- Web Application Security Testing
- Penetration Testing Practice
- Security Tool Experimentation

⚠️ Ethical Notice: This laboratory is intended only for educational purposes and authorized security testing. Never scan or attack systems without permission.

---

🏗️ Lab Architecture

<!-- Add your architecture screenshot here -->"Cybersecurity Lab Architecture" (1-screenshot-title-image.png)

Network Overview:

- Host Machine: Windows
- Virtualization Platform: VirtualBox
- Security Machine: Kali Linux
- Network Mode: NAT Network
- Private Network: 10.0.0.0/24

Additional target machines can be connected to the same NAT Network for future practical exercises.

---

⚙️ Lab Configuration

Component| Configuration
Host OS| Windows 10
Processor| Intel Core i7
Host RAM| 8 GB
Hypervisor| VirtualBox 7.2
Security OS| Kali Linux 2026.2
Kali RAM| 2048 MB
Network Type| NAT Network
Network Name| NatNetwork
Network Address| 10.0.0.0/24
Kali IP Address| 10.0.0.2/24
Default Gateway| 10.0.0.1
DNS Server| 8.8.8.8

---

🪜 Lab Setup Procedure

Step 1: Install 7-Zip

Installed 7-Zip to extract the Kali Linux virtual machine package.

Tool: "7-Zip" (https://www.7-zip.org/)

Step 2: Install VirtualBox

Installed Oracle VirtualBox as the virtualization platform for creating and managing virtual machines.

Tool: "VirtualBox" (https://www.virtualbox.org/wiki/Downloads)

Step 3: Create NAT Network

Created a dedicated NAT Network in VirtualBox.

Network Configuration:

Network Name: NatNetwork
IPv4 Prefix: 10.0.0.0/24
DHCP: Enabled
IPv6: Disabled

"NAT Network Configuration" (2-screenshot-network-settings-1.png)

A NAT Network allows multiple connected virtual machines to communicate with each other and access external networks through NAT.

Step 4: Import Kali Linux

Downloaded and imported the Kali Linux virtual machine into VirtualBox.

VM Configuration:

Operating System: Kali Linux
RAM: 2048 MB
Network Adapter: Adapter 1
Attached To: NAT Network
Network Name: NatNetwork
Adapter Type: Intel PRO/1000 MT Desktop

"Kali Linux Virtual Machine" (3-screenshot-kali-linux.png)

Configured a shared folder for transferring files between the host machine and Kali Linux.

Step 5: Configure Kali Linux Network

Configured and verified the IPv4 network settings in Kali Linux.

Network Configuration:

IP Address: 10.0.0.2
Subnet Mask: 255.255.255.0
Gateway: 10.0.0.1
DNS: 8.8.8.8

"Kali Network Configuration" (4-screenshot-kali-network-settings.png)

A consistent IP address helps identify the Kali machine during future network security exercises.

Step 6: Create a Clean VM Snapshot

Created a clean VirtualBox snapshot after completing the initial Kali Linux configuration.

Snapshot Name:

Clean Kali - Network Setup

This snapshot provides a recovery point and allows the virtual machine to return to its original configuration after future experiments.

---

🔎 Lab Verification

The following commands were used to verify the laboratory configuration.

Test| Command| Expected Result
Check IP Address| "ip a"| Correct IP displayed
Test Gateway| "ping 10.0.0.1"| Successful replies
Internet Connectivity| "ping 8.8.8.8"| Successful replies
DNS Resolution| "nslookup networkwalks.com"| Domain resolves
Verify Nmap| "nmap --version"| Version displayed
Snapshot Verification| Restore snapshot| Baseline restored

Example Network Details:

IP Address: 10.0.0.2/24
Gateway: 10.0.0.1
DNS Server: 8.8.8.8
Network: 10.0.0.0/24

---

🐞 Problems Encountered & Solutions

Problem 1: Internet Connectivity After Static IP Configuration

After configuring a static IP address, Internet connectivity may fail due to NetworkManager configuration.

One workaround explored:

sudo nmcli connection modify "Wired connection 1" ipv4.dad-timeout 0

Restarted the network connection and tested connectivity again.

Note: The connection name may differ. Check your actual connection name using:

nmcli connection show

Problem 2: VirtualBox VT-x Virtualization Error

The virtual machine initially failed to start because hardware virtualization was disabled in BIOS/UEFI.

Solution:

1. Restarted the computer.
2. Entered BIOS/UEFI settings.
3. Enabled Intel VT-x virtualization.
4. Saved the configuration.
5. Restarted the computer.
6. Started Kali Linux successfully.

---

💡 What I Learned

Through this project, I gained practical knowledge of virtualization, Linux networking, and cybersecurity lab configuration.

1. NAT vs NAT Network

Understood the difference between standard NAT and NAT Network and how multiple VMs can communicate through a shared NAT Network.

2. Virtual Machine Networking

Learned how VirtualBox network adapters connect virtual machines and how network modes affect communication.

3. Static IP Configuration

Learned about IPv4 addresses, subnet masks, default gateways, DNS servers, and network verification.

4. VM Snapshots

Understood how snapshots provide recovery points before performing experimental or risky activities.

5. Linux Networking Commands

Practiced commands such as:

ip a
ping
nslookup
nmcli
nmap --version

6. Technical Documentation

Learned the importance of documenting technical configurations, screenshots, commands, problems, and solutions.

---

🔐 Security & Ethical Use

This project is strictly for educational purposes and authorized cybersecurity testing.

All future penetration-testing activities will be conducted only in controlled lab environments or on systems where permission has been granted.

---

🔗 Tools & Resources

Tool| Official Website
7-Zip| https://www.7-zip.org/
VirtualBox| https://www.virtualbox.org/
Kali Linux| https://www.kali.org/get-kali/
Nmap| https://nmap.org/

---

👨‍💻 Author

Badal Kumar Sharma

🎓 Computer Science Engineering Student

🔐 Cybersecurity Enthusiast | Aspiring Penetration Tester

Training Program: Networkwalks Cybersecurity Program

Batch: B084

Project: Week 01 – Cybersecurity & Pentesting Lab Setup

---

🚀 Learning Journey

Currently learning and exploring:

- Ethical Hacking
- Kali Linux
- Network Security
- Penetration Testing
- Vulnerability Assessment
- Linux Administration
- Python for Cybersecurity

More cybersecurity projects coming soon!

---

<div align="center">🔐 Learn • Practice • Secure • Repeat

Thank you for visiting my repository!

⭐ If you find this project useful, consider giving it a star.

</div>
