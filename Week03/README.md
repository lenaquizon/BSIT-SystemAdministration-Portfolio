# Week 03: Portfolio Project Enterprise Server Deployment and Operating System Installation 

## Project Overview
Operating systems form the core foundation of enterprise IT infrastructure, enabling servers to host web services, databases, and business applications. In this project, acting in the role of a Junior System Administrator, an Ubuntu Server instance was deployed and configured for a startup environment. This documentation covers the end-to-end deployment process, including operating system installation, post-install configuration, system verification, and a technical comparison of modern boot architectures.

---

## Learning Objectives
After completing this project, students should be able to: 
### Knowledge 
Students should be able to: 
1. Explain the purpose of an operating system in enterprise environments. 
2. Differentiate BIOS and UEFI firmware. 
3. Explain the stages of the computer boot process. 
4. Compare Ubuntu Server, Windows Server, and Rocky Linux. 
### Skills 
Students should be able to: <br>
• Install Ubuntu Server in a virtual machine. <br>
• Configure server settings during installation. <br>
• Enable secure remote administration using SSH. <br>
• Verify server functionality. <br>
• Document installation procedures. <br>
• Produce professional technical documentation. <br>
### Professional Outcomes 
By the end of this activity, students will have: <br>
• Installed Ubuntu Server <br>
• Configured a working Linux server <br>
• Produced a deployment guide <br>
• Created installation documentation <br>
• Updated their GitHub portfolio <br>
• Published a LinkedIn learning reflection <br>

---

## Virtual Machine Specifications

| Feature | Specification |
| :--- | :--- |
| **Hypervisor** | VirtualBox |
| **Guest OS** | Ubuntu 25.04 LTS (or specified distro) |
| **vCPUs Assigned** | 2 Cores |
| **RAM Allocated** | 4 GB (4096 MB) |
| **Virtual Disk Size** | 40 GB |
| **Network Adapter** | NAT |

---

## Installation Summary
1. **Hypervisor Provisioning:**
• Launched Oracle VM VirtualBox and selected New.
• Defined VM Name as Ubuntu-Server-Week03 and attached the Ubuntu Server 25.04 ISO.
• Allocated 4 GB RAM, 2 vCPUs, and a 40 GB dynamic virtual disk.
• Configured the primary network adapter to NAT.

2. **System Setup & Profile Configuration:**
• Booted the VM and selected Ubuntu Server from the installation menu. <br>
• Configured primary language and keyboard layout to English (US). <br>
• Selected standard Ubuntu Server (Default) base package set. <br>
• Set up system credentials and profile parameters:<br>
    Administrator Name: YourName<br>
    Hostname: server01<br>
    Username: quizon<br>
    Password: Standard secure password<br>
• Enabled Install OpenSSH Server for remote administration capabilities.

3. **Finalization & Reboot:**
• Completed core package installation and selected Reboot Now.

---

## Configuration Summary
* **Hostname:** server01
* **Administrative Account:** quizon 
* **Primary Network Interface:** enp0s3 
* **Remote Access Service:** OpenSSH Server 

---

## Verification Results

1. **Host Identity Verification**
• Command: hostname<br>
• Expected Result: Output displays **server01**, matching assigned system identity.

2. **Network IP Assignment**
• Command: ip addr<br>
• Expected Result: Displays **enp0s3** interface with an assigned IPv4 address under the inet attribute.

3. **Outbound Network Connectivity**
• Command: ping -c 4 google.com<br>
• Expected Result: Transmits 4 ICMP packets returning 0% packet loss, confirming active internet access and functional DNS resolution.<br>

4. **Package Manager Synchronization**
• Command: sudo apt update && sudo apt upgrade -y <br>
• Expected Result: Synchronizes package lists successfully and upgrades outdated packages without broken dependencies.

5. **OpenSSH Service Daemon Status**
• Command: systemctl status ssh <br>
•Expected Result: Output indicates Active: active (running) in green text.<br>