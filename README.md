# 🛡️ NETWORKWALKS-B083-WK1-PM1-CYBERSECURITY-LAB-SETUP
## 🔐 Week 1 — Cybersecurity Lab Setup

Participant: B083
Program: Networkwalks Cybersecurity
Week: 01
Project: PM1 — Cybersecurity Lab Setup

## 📌 1. Project Overview

This project documents the setup of my cybersecurity laboratory environment for Week 1 of the Networkwalks Cybersecurity program.

The goal was to create a controlled virtual environment where I can safely practice networking, Linux administration, reconnaissance, and future cybersecurity exercises.

The lab was built using Oracle VirtualBox and Kali Linux. A dedicated VirtualBox NAT Network was configured with DHCP disabled and a manually assigned static IP address for Kali Linux.

## 🎯 2. Objectives

The main objectives of this lab were to:

🧰 Install the required software and utilities.
💻 Install and configure Oracle VirtualBox.
🌐 Create and configure a dedicated NAT Network.
🐉 Import and configure Kali Linux.
📍 Configure a static IP address.
🚪 Configure the gateway and DNS.
💾 Create a VirtualBox snapshot.
📡 Verify network connectivity and DNS resolution.
🧩 Troubleshoot a network connectivity issue.
🏗️ 3. Lab Architecture
                         🌍 Internet
                              |
                    🖥️ Windows 10 Host
                  Intel Core i7-3770
                       16 GB RAM
                              |
                 Oracle VirtualBox 7.2.16
                              |
              🔗 VirtualBox NAT Network
                   Network: 10.0.0.0/24
                    DHCP: Disabled
                              |
                     🐉 Kali Linux VM
                    IP: 10.0.0.2/24
                              |
                    Gateway: 10.0.0.1
                    DNS: 8.8.8.8
                         10.0.0.1
📸 Screenshot — Lab Architecture

[INSERT SCREENSHOT HERE — VIRTUALBOX NAT NETWORK / LAB ARCHITECTURE]

💻 4. System Configuration
🖥️ Host System
Component	Configuration
Operating System	Windows 10
Processor	Intel Core i7-3770
RAM	16 GB
Virtualization Software	Oracle VirtualBox 7.2.16
VirtualBox Build	r174877
GUI Framework	Qt 6.8.0
🐉 Virtual Machine
Component	Configuration
Operating System	Kali Linux 2026.2
Image	Kali Linux VirtualBox AMD64
Allocated RAM	8 GB
Network Mode	NAT Network
Network Name	VirtualBox NAT
IPv4 Network	10.0.0.0/24
DHCP	Disabled
IP Assignment	Manual / Static
Kali IP Address	10.0.0.2/24
Gateway	10.0.0.1
DNS Servers	8.8.8.8, 10.0.0.1
🧰 5. Tools and Software Used
🗜️ 7-Zip
💻 Oracle VirtualBox 7.2.16
🐉 Kali Linux 2026.2
🌐 NetworkManager / nmcli
📡 ping
🔎 ip
⚙️ 6. Installation and Setup
6.1 🗜️ Installing 7-Zip

7-Zip was installed on the Windows host system and used to extract the compressed files required for the virtual machine setup.

📸 Screenshot

[INSERT SCREENSHOT HERE — 7-ZIP INSTALLATION]

6.2 💻 Installing VirtualBox

Oracle VirtualBox was installed on the Windows 10 host system and used to run the Kali Linux virtual machine.

Installed version:

VirtualBox 7.2.16 r174877
Qt 6.8.0
📸 Screenshot

[INSERT SCREENSHOT HERE — VIRTUALBOX VERSION / INSTALLATION]

🌐 7. NAT Network Configuration

A dedicated VirtualBox NAT Network was created for the cybersecurity lab.

Network Name : VirtualBox NAT
IPv4 Network : 10.0.0.0/24
DHCP         : Disabled

DHCP was disabled because Kali Linux was configured with a manual/static IP address.

📸 Screenshot

[INSERT SCREENSHOT HERE — NAT NETWORK SETTINGS]

7.1 🐉 Importing Kali Linux

The Kali Linux 2026.2 VirtualBox AMD64 virtual machine was imported into VirtualBox and allocated 8 GB of RAM.

Its network adapter was connected to the VirtualBox NAT Network.

📸 Screenshot

[INSERT SCREENSHOT HERE — KALI VM SETTINGS / NETWORK ADAPTER]

📍 8. Kali Linux Network Configuration
8.1 🔢 Static IP Configuration

Kali Linux was configured with a manually assigned static IPv4 address:

IP Address : 10.0.0.2/24
Gateway    : 10.0.0.1
DNS        : 8.8.8.8
             10.0.0.1
📸 Screenshot

[INSERT SCREENSHOT HERE — KALI STATIC IP CONFIGURATION]

8.2 🔎 Checking the Network Interface

The following command was used to inspect the network interfaces and IP configuration:

ip a
📸 Screenshot

[INSERT SCREENSHOT HERE — OUTPUT OF ip a]

💾 9. VirtualBox Snapshot

After the initial configuration, a VirtualBox snapshot was created to preserve a known working state before continuing with future cybersecurity exercises.

📸 Screenshot

[INSERT SCREENSHOT HERE — VIRTUALBOX SNAPSHOT]

📡 10. Network and DNS Verification

Network connectivity and DNS resolution were tested using ping.

The following test was performed:

ping google.com

A successful response confirmed that the Kali machine could reach the network and resolve the domain name.

📸 Screenshot

[INSERT SCREENSHOT HERE — SUCCESSFUL ping google.com]

🧩 11. Troubleshooting
⚠️ Network Connectivity Problem

After configuring the static IP address, Kali Linux experienced a network connectivity problem.

The issue was resolved by modifying the NetworkManager connection profile and restarting the network connection.

sudo nmcli connection modify "Wired connection 1" ipv4.dad-timeout 0
sudo nmcli connection down "Wired connection 1"
sudo nmcli connection up "Wired connection 1"

After restarting the connection, connectivity was tested again with ping google.com.

📸 Screenshot

[INSERT SCREENSHOT HERE — nmcli COMMANDS / RESULTS]

✅ 12. Final Network Configuration
VirtualBox Network Type : NAT Network
Network Name            : VirtualBox NAT
Network Address         : 10.0.0.0/24
DHCP                    : Disabled

Kali Linux
IP Address              : 10.0.0.2/24
Default Gateway         : 10.0.0.1
DNS                     : 8.8.8.8 / 10.0.0.1
IP Assignment           : Static / Manual
📋 13. Verification Summary
Task	Status
🗜️ Installed 7-Zip	✅ Completed
💻 Installed VirtualBox	✅ Completed
🌐 Created NAT Network	✅ Completed
🚫 Disabled DHCP	✅ Completed
🐉 Imported Kali Linux VM	✅ Completed
📍 Configured static IP	✅ Completed
🚪 Configured gateway	✅ Completed
🌍 Configured DNS	✅ Completed
💾 Created VirtualBox snapshot	✅ Completed
📡 Tested connectivity with ping google.com	✅ Completed
📋 Ran ip a	✅ Completed
🧩 Troubleshot connectivity issue	✅ Completed
🧠 14. What I Learned

This lab gave me practical experience in setting up a controlled cybersecurity environment using virtualization.

I learned how to configure VirtualBox, create a NAT Network, connect Kali Linux to the network, and configure a static IPv4 address.

I also practiced basic Linux networking commands such as ip a, ping, and nmcli. The troubleshooting process helped me understand how to resolve a connectivity problem after changing network settings.

Creating a VirtualBox snapshot also demonstrated the importance of keeping a known working restore point before performing further experiments.

🔐 15. Security and Ethical Use

This laboratory environment is intended for legal and authorized cybersecurity learning and testing.

Any scanning, enumeration, exploitation, or other security testing should only be performed against systems and networks that I own or have explicit permission to test.

The virtual lab provides a controlled environment for practicing cybersecurity concepts while reducing the risk of unintentionally affecting external systems.

📚 16. Tools and Commands
Software
🗜️ 7-Zip
💻 Oracle VirtualBox
🐉 Kali Linux
🌐 NetworkManager
Commands
ip a
ping google.com
sudo nmcli connection modify "Wired connection 1" ipv4.dad-timeout 0
sudo nmcli connection down "Wired connection 1"
sudo nmcli connection up "Wired connection 1"
👨‍💻 17. Project Information

Program: Networkwalks Cybersecurity
Week: Week 1
Project: PM1 — Cybersecurity Lab Setup
Participant ID: B083
Repository: NETWORKWALKS-B083-WK1-PM1-CYBERSECURITY-LAB-SETUP

👤 18. Author

Ihtisham Khan

Cybersecurity | Networking | Python | IoT

🏁 19. Conclusion

The Week 1 Cybersecurity Laboratory Environment was successfully established using Kali Linux and Oracle VirtualBox.

The final environment uses a dedicated VirtualBox NAT Network with DHCP disabled and a manually configured Kali Linux address of:

10.0.0.2/24

Network connectivity and DNS resolution were successfully verified using ping google.com. A connectivity problem encountered during the static IP configuration was also resolved using NetworkManager commands.

This environment provides a controlled foundation for future Networkwalks cybersecurity exercises, networking practice, and security testing.
