# 🔐 Cybersecurity Lab Environment Setup

> **Task 01 — Setting Up a Cybersecurity & Penetration Testing Lab**

A controlled and isolated virtual environment for learning cybersecurity, ethical hacking, network reconnaissance, vulnerability assessment, and penetration testing.

---

## 📌 Project Overview

This project focuses on creating a virtual cybersecurity laboratory using **Oracle VirtualBox** and **Kali Linux**.

The purpose of this lab is to provide a safe and controlled environment where cybersecurity tools and techniques can be practiced without affecting unauthorized systems.

The laboratory uses a **private NAT Network**, allowing multiple virtual machines to communicate with each other while maintaining controlled external network connectivity.

Additional target machines can be added to the network in future cybersecurity tasks.

---

## 🎯 Objectives

The main objectives of this task are:

* Install and configure VirtualBox.
* Install/import Kali Linux as a virtual machine.
* Create a private NAT Network.
* Configure network connectivity for Kali Linux.
* Assign a consistent IP address to the Kali VM.
* Configure gateway and DNS settings.
* Verify network connectivity.
* Verify DNS resolution.
* Check cybersecurity tools such as Nmap.
* Create a clean VirtualBox snapshot.
* Document the complete laboratory setup.
* Prepare the environment for future cybersecurity projects.

---

## 🛡️ Purpose of the Lab

The laboratory provides an isolated environment for **cybersecurity education and authorized security testing**.

The environment can be used for:

* 🔎 Network reconnaissance
* 🌐 Network scanning
* 🚪 Port scanning
* 🛡️ Vulnerability assessment
* 📦 Packet analysis
* 🌍 Web security testing
* 💥 Exploitation practice
* 🧰 Security-tool experimentation
* 🧪 Future penetration-testing exercises

> ⚠️ **Important:** This laboratory must only be used for systems that you own or have explicit permission to test. Never use cybersecurity tools against unauthorized systems.

---

## 🏗️ Lab Architecture

```text
                     ┌───────────────────────┐
                     │     Host Computer     │
                     │       Windows        │
                     └───────────┬───────────┘
                                 │
                                 ▼
                     ┌───────────────────────┐
                     │      VirtualBox       │
                     │    Hypervisor Layer   │
                     └───────────┬───────────┘
                                 │
                                 ▼
                     ┌───────────────────────┐
                     │      NAT Network      │
                     │      10.0.0.0/24      │
                     └───────────┬───────────┘
                                 │
                  ┌──────────────┴──────────────┐
                  │                             │
                  ▼                             ▼
       ┌─────────────────────┐       ┌─────────────────────┐
       │     Kali Linux      │       │   Future Target VM  │
       │                     │       │                     │
       │ IP: 10.0.0.2        │       │ IP: 10.0.0.3+       │
       │ Security Testing    │       │ Vulnerable Systems  │
       └─────────────────────┘       └─────────────────────┘
```

Additional attacker and target machines can be connected to the same NAT Network during future authorized security-testing exercises.

---

## ⚙️ Lab Configuration

| Component          | Configuration          |
| ------------------ | ---------------------- |
| 🖥️ Host OS        | Windows 10/11          |
| 🧰 Hypervisor      | Oracle VirtualBox      |
| 🐉 Security OS     | Kali Linux             |
| 🧠 Kali RAM        | 2048 MB                |
| 🌐 Virtual Network | NAT Network            |
| 📡 Network Address | `10.0.0.0/24`          |
| 🐧 Kali IP Address | `10.0.0.2/24`          |
| 🚪 Default Gateway | `10.0.0.1`             |
| 🌍 DNS Server      | `8.8.8.8`              |
| 🔮 Future VM Range | `10.0.0.3 – 10.0.0.99` |

---

# 🪜 Lab Setup Procedure

## Step 1 — Install 7-Zip

7-Zip was installed to extract the Kali Linux virtual-machine package when distributed as a `.7z` archive.

**Tool:** 7-Zip

<img width="1920" height="1080" alt="Screenshot (266)" src="https://github.com/user-attachments/assets/9056b465-e187-42a2-9caf-d508b8d796ae" />


---

## Step 2 — Install VirtualBox

Oracle VirtualBox was installed as the hypervisor for running the Kali Linux virtual machine.

VirtualBox provides the virtualization layer required to create and manage the cybersecurity laboratory.

<img width="1920" height="1080" alt="Screenshot (267)" src="https://github.com/user-attachments/assets/e9260a5e-248f-4a97-a5c4-f18c31e53664" />


---

## Step 3 — Create the NAT Network

A dedicated NAT Network was created in VirtualBox.

### Network Configuration

```text
Network Name : NatNetwork
IPv4 Prefix  : 10.0.0.0/24
DHCP         : Enabled
IPv6         : Disabled
```
<img width="1920" height="1080" alt="Screenshot (264)" src="https://github.com/user-attachments/assets/59116c35-e802-403b-a99c-e415107b0747" />


A NAT Network was selected because multiple virtual machines connected to the same NAT Network can communicate with each other while also having outbound network connectivity.

This configuration allows additional attacker and target machines to be added later.

---

## Step 4 — Import Kali Linux

Kali Linux was downloaded and imported into VirtualBox.

The VM network adapter was configured as follows:

```text
Adapter 1
Attached to : NAT Network
Network     : NatNetwork
```

The Kali Linux VM was allocated:

```text
RAM : 2048 MB
```
<img width="1920" height="1080" alt="Screenshot (263)" src="https://github.com/user-attachments/assets/79fca42b-c538-421c-8a99-d2d79f22f520" />


A shared folder was also configured for transferring required files between the host operating system and the Kali Linux VM.

---

## Step 5 — Configure Kali Linux Network

The Kali Linux network configuration was checked and configured with a consistent IPv4 address.

### Network Configuration

```text
IP Address    : 10.0.0.2
Subnet Mask   : 255.255.255.0
Gateway       : 10.0.0.1
DNS           : 8.8.8.8
```
<img width="1920" height="1080" alt="Screenshot (265)" src="https://github.com/user-attachments/assets/6308dafd-9490-46e2-b21c-3155a68d6861" />


Using a consistent IP address makes it easier to identify and document the Kali Linux machine during future laboratory exercises.

---

## Step 6 — Create a Clean VM Snapshot

After completing the initial configuration, a VirtualBox snapshot was created.

### Snapshot Name

```text
Clean Kali - Network Setup
```
<img width="1920" height="1080" alt="Screenshot (261)" src="https://github.com/user-attachments/assets/8fce1281-710c-4eb7-a972-3c7d3e282695" />


The snapshot represents the clean baseline of the cybersecurity laboratory.

If a future experiment modifies or damages the VM configuration, the machine can be restored to this known-good state.

---

# 🔎 Lab Verification

The following commands were used to verify the laboratory configuration.

| Test                | Command                   | Expected Result        |
| ------------------- | ------------------------- | ---------------------- |
| 🌐 Check IP address | `ip a`                    | Kali IP displayed      |
| 📡 Test gateway     | `ping 10.0.0.1`           | Successful replies     |
| 🌍 Test Internet    | `ping 8.8.8.8`            | Successful replies     |
| 🔎 Test DNS         | `nslookup example.com`    | Domain resolves        |
| 🧰 Verify Nmap      | `nmap --version`          | Nmap version displayed |
| 🔄 Verify snapshot  | Restore snapshot + `ip a` | Baseline restored      |

### Example Results

```text
IP Address:
10.0.0.2/24

Gateway:
10.0.0.1

DNS:
8.8.8.8
```

---

# 🐞 Problems Encountered & Solutions

## Problem 1 — Internet Connectivity After Static IP Configuration

After manually configuring IPv4 settings, Internet connectivity may fail depending on the Kali Linux and NetworkManager configuration.

One workaround used during the laboratory setup was:

```bash
sudo nmcli connection modify "Wired connection 1" ipv4.dad-timeout 0
```

The network connection was then restarted and connectivity was tested again.

> **Note:** Network interface and connection names can differ between systems. Always identify the actual connection name before modifying it with `nmcli`.

---

## Problem 2 — VirtualBox VT-x / Hardware Virtualization Error

The Kali Linux VM initially failed to start because hardware virtualization was disabled in the system firmware/BIOS.

### Solution

1. Restart the computer.
2. Enter BIOS/UEFI settings.
3. Enable Intel VT-x / hardware virtualization.
4. Save the configuration.
5. Restart the computer.
6. Start the Kali Linux VM again.

After enabling hardware virtualization, the VM started successfully.

---

# 💡 What I Learned

Through this project, I learned how to create and configure a virtual environment for cybersecurity practice.

### 1. NAT vs NAT Network

I learned that standard **NAT** and **NAT Network** configurations serve different purposes.

A NAT Network allows multiple virtual machines connected to the same virtual network to communicate with one another while providing network address translation for external connectivity.

This makes it useful for building a multi-machine cybersecurity laboratory.

### 2. Virtual Machine Networking

I learned how VirtualBox network adapters connect virtual machines to different types of networks and how network configuration affects communication between machines.

### 3. Static IP Configuration

I learned how to configure and verify:

* IPv4 addresses
* Subnet masks
* Default gateways
* DNS servers

in Kali Linux.

### 4. VM Snapshots

I learned the importance of creating a clean VM snapshot before performing risky or experimental cybersecurity activities.

Snapshots provide a known-good recovery point.

### 5. Cybersecurity Lab Isolation

I learned why security-testing activities should be performed inside controlled environments.

An isolated lab allows cybersecurity tools and techniques to be tested safely without targeting unauthorized systems.

### 6. Documentation

I learned that documenting configuration, commands, screenshots, problems, and solutions is an important part of professional cybersecurity work.

---

# 🔐 Security & Ethical Use

This project is created strictly for **educational and authorized cybersecurity testing**.

The tools and techniques used in this laboratory should only be applied to:

* Systems owned by the tester.
* Intentionally vulnerable laboratory machines.
* Systems for which explicit testing permission has been obtained.

> ⚠️ **Never perform unauthorized scanning, exploitation, or security testing against real-world systems.**

---

# 🧰 Tools Used

* **Oracle VirtualBox** — Virtualization platform
* **Kali Linux** — Security testing operating system
* **7-Zip** — Archive extraction
* **Nmap** — Network scanning and reconnaissance
* **NetworkManager / nmcli** — Linux network configuration
* **VirtualBox Snapshots** — VM recovery

---

# 🔗 Tools & Resources

* 7-Zip: https://7-zip.org/download.html
* VirtualBox: https://www.virtualbox.org/wiki/Downloads
* Kali Linux: https://www.kali.org/get-kali/

---

# 📂 Repository Structure

```text
NetworkWalks-BO82-Week1-Cybersecurity-Lab-Setup/
│
├── README.md
├── kali-nat-network.png
├── virtualbox.png
├── vm-nat-network.png
├── kali-interface.png
├── kali-network-config.png
└── clean-snapshot.png
```

---

# 🚀 Future Improvements

The laboratory can be expanded in future cybersecurity tasks by adding:

* 🐧 Additional Linux target machines
* 🪟 Windows target VM
* 🎯 Intentionally vulnerable machines
* 🌐 Vulnerable web applications
* 🕵️ Network traffic analysis
* 🔎 Vulnerability scanning
* 🧪 Exploitation practice
* 🛡️ Defensive security monitoring
* 📊 Security monitoring dashboards

Possible future lab architecture:

```text
                  Cybersecurity Lab
                         │
                  ┌──────┴──────┐
                  │ NAT Network │
                  │ 10.0.0.0/24 │
                  └──────┬──────┘
                         │
        ┌────────────────┼────────────────┐
        │                │                │
        ▼                ▼                ▼
   Kali Linux       Linux Target     Windows Target
   10.0.0.2         10.0.0.3+        10.0.0.4+
   Attacker         Vulnerable       Vulnerable
```

---

# 📌 Project Information

| Field           | Details                                       |
| --------------- | --------------------------------------------- |
| 🎓 Program      | Cybersecurity at NetworkWalks                 |
| 🔐 Category     | Cybersecurity & Ethical Hacking               |
| 📚 Task         | Task 01                                       |
| 🧪 Project      | Cybersecurity & Penetration Testing Lab Setup |
| 🖥️ Environment | VirtualBox + Kali Linux                        |
| 🌐 Network      | NAT Network                                   |
| 📁 Repository   | GitHub                                        |

---

## 👤 Author

**Muhammad Ibrahim | (NURUDDEEN)**

Cybersecurity Student | NetworkWalks B082

### 🎯 Interests

Cybersecurity • Ethical Hacking • Network Security • Linux • Penetration Testing

### 🎓 Training

**NetworkWalks Cybersecurity Training — B082**

Currently developing practical skills in:

- Cybersecurity fundamentals
- Network security
- Linux administration
- Virtualization
- Penetration testing
- Network reconnaissance
- Security tools and laboratory environments

### 👨‍🏫 Mentor

**Waqas Karim (CCIE)**

Thank you for the technical guidance and practical learning opportunity throughout the training.

---

## 📊 Project Progress

**6 / 6 Steps Completed ✅**

> 🔐 Learn • Practice • Build • Secure

**NetworkWalks Cybersecurity Training — Week 01**

This project represents my first practical cybersecurity laboratory setup and provides the foundation for future security-testing and networking projects.

---

## ⭐ Acknowledgement

This project was completed as part of my **NetworkWalks B082 Cybersecurity Training**.

I would like to thank my mentor, **Waqas Karim (CCIE)**, for the technical guidance and practical learning opportunity.

---

## 🚀 Cybersecurity Journey — Task 01

**Set up the lab. Learn the tools. Practice safely. Build responsibly.**
