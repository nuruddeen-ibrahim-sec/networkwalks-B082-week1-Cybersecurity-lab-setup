<div align="center">

# 🔐 Cybersecurity Lab Environment Setup

**Building a controlled virtual environment for cybersecurity learning and authorized security testing**

</div>

<p align="center">
  <img src="https://img.shields.io/badge/Cybersecurity-Student-C00000?style=flat-square" />
  <img src="https://img.shields.io/badge/VirtualBox-7.2-0070C0?style=flat-square" />
  <img src="https://img.shields.io/badge/Kali%20Linux-2026.2-E87500?style=flat-square&logo=kalilinux&logoColor=white" />
  <img src="https://img.shields.io/badge/Network-10.0.0.0%2F24-238F89?style=flat-square" />
  <img src="https://img.shields.io/badge/Linux-Cybersecurity-C00000?style=flat-square" />
  <img src="https://img.shields.io/badge/NetworkWalks-B082-C00000?style=flat-square" />
</p>

---

## 📌 Project Overview

This project is my Week 1 cybersecurity laboratory setup completed as part of the NetworkWalks B082 training program.

The goal was to build a controlled virtual environment using VirtualBox and Kali Linux that can be used for cybersecurity learning, networking practice, and authorized security testing.

The laboratory uses a private virtual network so that additional virtual machines can be added for future practical exercises.

---

## 🎯 Objectives

The main objectives of this project were to:

- Set up a cybersecurity laboratory environment.
- Install and configure VirtualBox.
- Import and configure Kali Linux.
- Create a private NAT Network.
- Configure Kali Linux networking.
- Verify network connectivity.
- Create a clean VM snapshot.
- Document the setup process.
- Prepare the environment for future cybersecurity practicals.

---

## 🛡️ Purpose of the Lab

The laboratory provides a controlled environment for cybersecurity learning and authorized security testing.

It can be used for activities such as:

- Network reconnaissance
- Port scanning
- Vulnerability assessment
- Packet analysis
- Web security testing
- Security-tool practice
- Linux and networking exercises

⚠️ **Important:** This laboratory should only be used against systems that I own or have explicit permission to test.

---

## 🏗️ Lab Architecture

![Lab Architecture](1-screenshot-title-image.png)

The laboratory is designed so that additional virtual machines can be connected to the same private network for future authorized security exercises.

---

## ⚙️ Lab Configuration

| Component | Configuration |
|---|---|
| 🖥️ Host OS | Windows 10 |
| 🧰 Hypervisor | VirtualBox 7.2 |
| 🐉 Security OS | Kali Linux 2026.2 |
| 🧠 Kali RAM | 2048 MB |
| 🌐 Virtual Network | NAT Network |
| 📡 Network Address | 10.0.0.0/24 |
| 🐧 Kali IP Address | 10.0.0.2/24 |
| 🚪 Default Gateway | 10.0.0.1 |
| 🌍 DNS Server | 8.8.8.8 |
| 🔮 Future VM Range | 10.0.0.3–10.0.0.99 |

> **Note:** Host hardware specifications will be added based on my actual laptop configuration.

---

# 🪜 Lab Setup Procedure

## Step 1: Install 7-Zip

7-Zip was installed to extract the compressed files required for the cybersecurity laboratory setup.

### Process

1. Download 7-Zip.
2. Install it on the host computer.
3. Confirm that the installation completed successfully.
4. Extract the required laboratory files.

### Evidence

![7-Zip Installation](screenshots/01-7zip.png)

---

## Step 2: Install VirtualBox

VirtualBox was installed as the virtualization platform for the cybersecurity laboratory.

### Process

1. Download VirtualBox.
2. Install VirtualBox on the host computer.
3. Launch VirtualBox.
4. Confirm that the application opens correctly.

### Evidence

![VirtualBox](screenshots/02-virtualbox.png)

---

## Step 3: Create the NAT Network

A dedicated NAT Network was configured in VirtualBox for the cybersecurity laboratory.

### Network Configuration

```text
Network Name: NatNetwork
IPv4 Prefix:  10.0.0.0/24
DHCP:         Enabled
IPv6:         Disabled
