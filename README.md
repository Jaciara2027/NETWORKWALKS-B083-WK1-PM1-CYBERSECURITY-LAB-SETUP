#🔐 Cybersecurity Lab Environment Setup

> A practical cybersecurity testing lab was built with VirtualBox and Kali Linux, following the Week 1 Project Module 1 lab guide.
---------------------------
## 📌 Project Overview
> This project focused on setting up a controlled virtual environment for
cybersecurity and ethical-hacking practice.
The laboratory used VirtualBox as the virtualization platform and
Kali Linux as the attacking/security-testing machine. The virtual
network is configured using a NAT Network with the 10.0.0.0/24
subnet.
------------------------------------------------------------------------

## 🎯 Objectives

The main objectives of this lab were to:

-   Install and configure 7-Zip;
-   Install VirtualBox;
-   Create a NAT Network using the 10.0.0.0/24 subnet;
-   Import Kali Linux into VirtualBox;
-   Configure Kali Linux with the required IP address;
-   Provide Kali Linux with Internet access;
-   Create a VM snapshot after the initial setup.

------------------------------------------------------------------------

## 🏗️ Lab Architecture

### Main Environment

 |Component                    |   Configuration
 |-----------------------------|------------------------
 | Host OS                     |    Windows 11 Pro |
 |Virtualization Platform      |  VirtualBox   |
 |Security / Attacking Machine |  Kali Linux   |
 |Virtual Network              | NAT Network   |
 |Network Address              |  `10.0.0.0/24`  |
 |Kali Linux IP                | `10.0.0.2/24`   |
 |DNS Server                   |  `8.8.8.8`      |
 |Gateway                      |   `10.0.0.1`    |
 | NetMask                     |  `24`           |

Recommended Host Specifications
The guide recommended, but did not require:
-   RAM: 8 GB or more
-   Storage:256 GB SSD or more
-   Processor: Intel Core i3/i5 or similar

------------------------------------------------------------------------

## 🛡️ Purpose of the Lab

Kali Linux was configured as the main security-testing machine.

------------------------------------------------------------------------

## 🪜 Lab Setup Procedure

### Step 1 - Install 7-Zip

7-Zip was installed on the host computer.

7-Zip was used to extract compressed files required for the
virtual-machine setup.

Download:
https://7-zip.org/download.html

------------------------------------------------------------------------

### Step 2 - Install VirtualBox

Oracle VirtualBox was installed on the host computer.

VirtualBox was used as the base virtualization platform for the
cybersecurity laboratory.

Download:
https://virtualbox.org/wiki/Downloads

------------------------------------------------------------------------

### Step 3 - Create the NAT Network

A custom NAT Network was created in VirtualBox.

Required network configuration :
```text
Network: NATNetwork
IPv4 Prefix: 10.0.0.0/24
Enable DHCP
```

The NAT Network was configured to use the
10.0.0.0/24 subnet.

<img width="1308" height="948" alt="Captura de ecrã 2026-09-10 155429" src="https://github.com/user-attachments/assets/c480134d-08ec-484b-a4df-b8050b8dce7d" />

This network was used by Kali Linux.

<img width="1916" height="1004" alt="Captura de ecrã 2026-09-10 185305" src="https://github.com/user-attachments/assets/0d9903df-316b-489d-a56b-19709e91db58" />



------------------------------------------------------------------------

### Step 4 - Download and Import Kali Linux

The Kali Linux virtual machine was downloaded and imported into VirtualBox.

Download Link:
https://kali.org/get-kali

After importing the VM, its network adapter was configured to use the
previously created NAT Network.

Kali Linux network
``` text
Network: NATNetwork
IP Address: 10.0.0.2/24
```


------------------------------------------------------------------------

### Step 5 - Configure Kali Linux

<img width="945" height="1025" alt="Captura de ecrã 2026-09-10 193645" src="https://github.com/user-attachments/assets/9abfed9b-2842-4037-acd3-7ac823268f8e" />


Kali Linux was configured according to the lab requirements.
The required Kali Linux address is:
IP Address: 10.0.0.2/24

Kali Linux was configured to have full Internet
access.

When Internet connectivity caused problems, the following checks were performed:

1.  Whether the NAT Network had been created correctly.
2.  Whether the VirtualBox network settings were correct.
3.  Whether another VM was already using `10.0.0.2`.
4.  Restarting the relevant virtual machines and the host operating
    system.

------------------------------------------------------------------------

## 🌐 Internet Connectivity Troubleshooting

When Internet connectivity problems
occur it was used the following command to solve :
sudo nmcli connection modify "Wired connection 1" ipv4.dad-timeout 0

-------------------------------------------------------------------------

### Step 6 - Create a VM Snapshot

After completing the initial Kali Linux configuration, a
VirtualBox snapshot.

The snapshot provided a recovery point that could be used in the futur.

------------------------------------------------------------------------

# 🔎 Lab Verification

The following items were verified before considering the environment ready:

 | Check                |  Expected Configuration |
 |----------------------|------------------------ |
 |VirtualBox installed  | ✅                      |
 |NAT Network created   | `10.0.0.0/24`           |
 |Kali Linux imported   | ✅                       |
 | Kali IP address      |  `10.0.0.2/24`             |
 | Internet access      |  Available               |
 | VM snapshot          |  Created                 |


------------------------------------------------------------------------

# 🐞 Common Problems and Checks

## Problem 1 - Kali Linux has no Internet

What was Checked:

-   NAT Network configuration.
-   Kali Linux network adapter.
-   IP address configuration.
-   Whether another VM is using `10.0.0.2`.
-   VirtualBox network settings.
-   Host and VM restart status.

when required, the `nmcli` command shown in the Internet
Connectivity Troubleshooting section was aplyed.

------------------------------------------------------------------------

## Problem 2 - Network configuration does not work

Verify that:

``` text
Network type: NAT Network
Subnet: 10.0.0.0/24
Kali IP: 10.0.0.2/24
```

Also make sure that another virtual machine is not using the same IP
address.

------------------------------------------------------------------------

# 📚 What This Lab Covers

By completing this setup, the following concepts were practiced:
1. Virtualization

VirtualBox was used to create and manage virtual machines.
2. Virtual Networking

A NAT Network was created and configured using:
10.0.0.0/24

3. Kali Linux

Kali Linux was set up as the main cybersecurity testing machine.

4. Network Configuration

A specific IP address was configured:
10.0.0.2/24

5. VM Snapshots

A snapshot was created after the initial configuration so the VM could be
restored before future exercises.

------------------------------------------------------------------------

# 🔗 Tools & Resources

-   7-Zip: https://7-zip.org/download.html
-   VirtualBox: https://virtualbox.org/wiki/Downloads
-   Kali Linux: https://kali.org/get-kali

------------------------------------------------------------------------

#📌 Project Information

Task: WK1-PM1
Module: Project Module 1
Lab: Cybersecurity Testing Lab Setup
Virtualization: VirtualBox
Security OS: Kali Linux
Network:10.0.0.0/24
Kali IP:10.0.0.2/24



