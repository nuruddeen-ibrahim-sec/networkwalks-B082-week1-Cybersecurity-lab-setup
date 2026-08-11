# Cybersecurity Lab Setup

## NetworkWalks | Week 1 Cybersecurity Project

I completed my first hands-on cybersecurity project as part of the NetworkWalks B082 training program.

The project focused on setting up a practical cybersecurity lab environment and preparing it for future cybersecurity and networking exercises.

## Project Objectives

- Set up a cybersecurity lab environment
- Configure the network environment
- Install and configure Kali Linux
- Verify network connectivity
- Prepare the environment for future cybersecurity practicals
- Document the setup process and troubleshooting steps

## Tools Used

- Kali Linux
- VirtualBox
- Linux networking tools
- GitHub

- ## Step 1: Download and Install 7-Zip

7-Zip was downloaded and installed on the host computer.

7-Zip was required to extract the compressed cybersecurity lab files before setting up the virtual machine environment.

### Installation

1. Download 7-Zip from the official website.
2. Install 7-Zip on the host computer.
3. Confirm that the installation completed successfully.
4. Use 7-Zip to extract the required lab files.

### Verification

After installation, 7-Zip was available on the host system and ready to extract the required files.

> Screenshot: Add a screenshot showing the 7-Zip installation or the extracted lab files here.

## Step 2: Install and Configure VirtualBox

VirtualBox was used to create and manage the virtual machine for the cybersecurity lab.

### Installation

I downloaded and installed Oracle VirtualBox on the host computer.

### VirtualBox Configuration

After installation, I opened VirtualBox and prepared the networking configuration for the Kali Linux virtual machine.

The lab network was configured using a NAT Network.

| Configuration | Value |
|---|---|
| Network Type | NAT Network |
| Network Name | CyberLab-Network |
| Network Range | 10.0.0.0/24 |
| DHCP | Enabled |
| Purpose | Isolated cybersecurity lab |

### Why NAT Network?

The NAT Network allows the virtual machines in the lab to communicate with each other while keeping the lab environment separated from the main network.

### Verification

I verified that the NAT Network was created successfully in VirtualBox and was available for the Kali Linux virtual machine.

### Screenshot

![VirtualBox Network Configuration](screenshots/virtualbox-network.png)

### Notes

This configuration was created as part of the NetworkWalks Week 1 cybersecurity lab setup. The environment will be used for authorized cybersecurity learning and testing only.
