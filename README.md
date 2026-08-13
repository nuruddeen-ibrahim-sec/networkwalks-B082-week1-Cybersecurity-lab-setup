<div align="center">

# 🔐 Cybersecurity Lab Environment Setup

**NetworkWalks B082 — Week 1 | Task 01**

**Building an isolated virtual cybersecurity laboratory using VirtualBox and Kali Linux**

</div>

---

## 📌 Project Overview

This project is part of my **NetworkWalks B082 cybersecurity training program**.

The goal of this task was to build a controlled cybersecurity laboratory using **Oracle VirtualBox and Kali Linux**.

The laboratory provides an isolated environment where I can practice cybersecurity concepts, networking, reconnaissance, vulnerability assessment, packet analysis, and other authorized security-testing activities.

The lab uses a private **NAT Network (10.0.0.0/24)** so that additional virtual machines can be connected in future projects.

---

## 🎯 Project Objectives

The main objectives of this project were:

- Install and configure 7-Zip.
- Install and configure Oracle VirtualBox.
- Create a private NAT Network.
- Import Kali Linux into VirtualBox.
- Configure the Kali Linux network adapter.
- Configure IPv4 networking.
- Verify connectivity between the Kali VM and gateway.
- Test Internet and DNS connectivity.
- Verify security tools such as Nmap.
- Create a clean VirtualBox snapshot.
- Document the complete laboratory setup.
- Prepare the environment for future cybersecurity exercises.

---

## 🛡️ Purpose of the Lab

The laboratory provides a controlled environment for cybersecurity education and authorized security testing.

It can be used for:

- 🔎 Network reconnaissance
- 🌐 Network scanning
- 🚪 Port scanning
- 🛡️ Vulnerability assessment
- 📦 Packet analysis
- 🌍 Web security testing
- 🧪 Security-tool experimentation
- 💻 Linux security practice
- 🔐 Future penetration-testing exercises

> ⚠️ **Important:** This laboratory should only be used against systems that I own or have explicit permission to test.

---

# 🏗️ Lab Architecture

```text
                    ┌─────────────────────────┐
                    │      Host Computer      │
                    │       Windows OS        │
                    └────────────┬────────────┘
                                 │
                                 ▼
                    ┌─────────────────────────┐
                    │       VirtualBox         │
                    │     Hypervisor Layer     │
                    └────────────┬────────────┘
                                 │
                                 ▼
                    ┌─────────────────────────┐
                    │       NAT Network        │
                    │       10.0.0.0/24        │
                    └────────────┬────────────┘
                                 │
                    ┌────────────┴────────────┐
                    │                         │
                    ▼                         ▼
           ┌─────────────────┐       ┌─────────────────┐
           │    Kali Linux   │       │  Future Target  │
           │                 │       │       VM        │
           │ 10.0.0.2/24     │       │ 10.0.0.3+       │
           │ Security Lab    │       │ Lab Target      │
           └─────────────────┘       └─────────────────┘

The current laboratory contains the Kali Linux virtual machine.

Additional target machines can be connected to the same NAT Network during future authorized cybersecurity exercises.


---

⚙️ Lab Configuration

Component	Configuration

🖥️ Host OS	Windows
🧰 Hypervisor	Oracle VirtualBox
🐉 Security OS	Kali Linux
🧠 Kali RAM	2048 MB
🌐 Virtual Network	NAT Network
📡 Network Address	10.0.0.0/24
🐧 Kali IP Address	10.0.0.2/24
🚪 Default Gateway	10.0.0.1
🌍 DNS Server	8.8.8.8
🔮 Future VM Range	10.0.0.3 – 10.0.0.99



---

🪜 Lab Setup Procedure

Step 1 — Install 7-Zip

7-Zip was installed to extract the Kali Linux virtual-machine files when provided as a compressed archive.

Tool: 7-Zip

Screenshot




---

Step 2 — Install Oracle VirtualBox

Oracle VirtualBox was installed as the virtualization platform for the cybersecurity laboratory.

VirtualBox allows virtual machines to run independently from the host operating system.

Screenshot




---

Step 3 — Create the NAT Network

A dedicated NAT Network was created in VirtualBox for the cybersecurity laboratory.

Network Configuration

Network Name : NatNetwork
IPv4 Prefix  : 10.0.0.0/24
DHCP         : Enabled
IPv6         : Disabled

Screenshot



The NAT Network allows virtual machines connected to the same network to communicate with each other while providing controlled external connectivity.

This configuration also allows additional target machines to be added later.


---

Step 4 — Import Kali Linux

The Kali Linux virtual machine was imported into Oracle VirtualBox.

The VM network adapter was connected to the previously created NAT Network.

Network Adapter

Adapter 1
Attached to : NAT Network
Network     : NatNetwork

The Kali Linux VM was allocated:

RAM : 2048 MB

Screenshot



The Kali Linux virtual machine provides the main security-testing environment for this project.


---

Step 5 — Configure the Kali Linux Network

The Kali Linux network configuration was checked and configured for the laboratory network.

Network Configuration

IP Address   : 10.0.0.2
Subnet Mask  : 255.255.255.0
Gateway      : 10.0.0.1
DNS Server   : 8.8.8.8

Screenshot



A consistent IP address makes it easier to identify the Kali Linux machine during future laboratory exercises.


---

Step 6 — Verify the Kali Network Interface

The Kali network interface was checked from the terminal to confirm that the expected address was assigned.

Example command:

ip a

The expected Kali address is:

10.0.0.2/24

Screenshot




---

Step 7 — Create a Clean VM Snapshot

After completing the initial laboratory configuration, a clean VirtualBox snapshot was created.

Snapshot Name

Clean Kali - Network Setup

Screenshot



The snapshot provides a known-good recovery point.

If a future cybersecurity experiment changes the VM configuration, the Kali machine can be restored to this baseline.


---

🔎 Lab Verification

The laboratory configuration was verified using basic networking commands.

Test	Command	Expected Result

🌐 Check IP address	ip a	Kali IP displayed
📡 Test gateway	ping 10.0.0.1	Successful replies
🌍 Test Internet	ping 8.8.8.8	Successful replies
🔎 Test DNS	nslookup example.com	Domain resolves
🧰 Verify Nmap	nmap --version	Nmap version displayed


Example Network Details

Kali IP Address:
10.0.0.2/24

Gateway:
10.0.0.1

DNS:
8.8.8.8


---

🐞 Problems Encountered & Solutions

Problem 1 — Network Configuration

During the laboratory setup, network configuration required checking the assigned interface, IP address, gateway, and DNS settings.

Verification

ip a
ip route

The network configuration was checked before continuing with the laboratory setup.


---

Problem 2 — VirtualBox Network Configuration

The Kali Linux VM needed to be connected to the correct NAT Network before communication with the laboratory gateway could be tested.

Solution

The VirtualBox network adapter was checked and configured as:

Attached to : NAT Network
Network     : NatNetwork

The Kali network was then tested again.


---

💡 What I Learned

1. Virtual Machine Networking

I learned how virtual machines communicate through VirtualBox network adapters and how different network modes affect connectivity.


---

2. NAT Network

I learned that a NAT Network can allow multiple virtual machines to communicate with each other while providing external network connectivity.

This is useful for creating a multi-machine cybersecurity laboratory.


---

3. IPv4 Configuration

I learned how to identify and verify:

IPv4 Address
Subnet Mask
Default Gateway
DNS Server

in Kali Linux.


---

4. VirtualBox Snapshots

I learned why a clean snapshot is useful before performing experimental cybersecurity activities.

A snapshot provides a known-good recovery point.


---

5. Cybersecurity Lab Isolation

I learned the importance of performing security testing inside a controlled environment.

An isolated laboratory makes it possible to practice cybersecurity techniques without targeting unauthorized systems.


---

6. Technical Documentation

I learned that documenting commands, configurations, screenshots, problems, and solutions is an important part of professional cybersecurity work.


---

🔐 Security & Ethical Use

This laboratory was created for educational and authorized cybersecurity testing.

The environment should only be used against:

Systems that I own.

Intentionally vulnerable laboratory machines.

Systems where explicit testing permission has been provided.


> ⚠️ Never perform unauthorized scanning, exploitation, or security testing against real-world systems.




---

🧰 Tools Used

Oracle VirtualBox — Virtualization platform

Kali Linux — Cybersecurity testing operating system

7-Zip — Archive extraction

Nmap — Network scanning

NetworkManager / nmcli — Linux network configuration

VirtualBox Snapshots — VM recovery

GitHub — Project documentation and version control



---

🔗 Tools & Resources

7-Zip — https://7-zip.org/download.html

VirtualBox — https://www.virtualbox.org/wiki/Downloads

Kali Linux — https://www.kali.org/get-kali/



---

📂 Repository Structure

networkwalks-B082-week1-Cybersecurity-lab-setup/
│
├── README.md
│
├── 7zip.png
├── VirtualBox.png
├── VMNATNetwork.png
├── KaliInterface.png
├── KaliNetworkConfig.png
├── KaliNATNetwork.png
└── CleanSnapshot.png

The screenshots document the major stages of the laboratory setup.


---

🚀 Future Improvements

The laboratory can be expanded in future cybersecurity projects by adding:

🐧 Additional Linux target machines

🪟 Windows target VM

🎯 Intentionally vulnerable machines

🌐 Vulnerable web applications

📦 Network traffic analysis

🔎 Vulnerability scanning

🧪 Authorized exploitation practice

🛡️ Defensive security monitoring

📊 Security monitoring tools


Future Lab Concept

Cybersecurity Lab
                        │
                 ┌──────┴──────┐
                 │ NAT Network │
                 │ 10.0.0.0/24 │
                 └──────┬──────┘
                        │
          ┌─────────────┼─────────────┐
          │             │             │
          ▼             ▼             ▼
     Kali Linux    Linux Target   Windows Target
      10.0.0.2      10.0.0.3+       10.0.0.4+
      Security       Lab Target      Lab Target


---

📌 Project Information

Field	Details

🎓 Program	NetworkWalks B082 Cybersecurity Training
🔐 Category	Cybersecurity & Ethical Hacking
📚 Task	Week 1 — Task 01
🧪 Project	Cybersecurity Lab Environment Setup
🖥️ Environment	VirtualBox + Kali Linux
🌐 Network	NAT Network
📡 Network Range	10.0.0.0/24
🐧 Kali Address	10.0.0.2/24
📁 Repository	GitHub
👤 Author	Muhammad Ibrahim



---

⭐ Acknowledgement

This project was completed as part of my NetworkWalks B082 cybersecurity training journey.

It provides the foundation for future practical cybersecurity and networking exercises.


---

🔐 Cybersecurity Journey — Task 01

Build the lab. Learn the tools. Practice safely. Build responsibly.
