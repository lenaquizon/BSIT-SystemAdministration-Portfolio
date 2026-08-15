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
Students should be able to: 
• Install Ubuntu Server in a virtual machine. 
• Configure server settings during installation. 
• Enable secure remote administration using SSH. 
• Verify server functionality. 
• Document installation procedures. 
• Produce professional technical documentation. 
### Professional Outcomes 
By the end of this activity, students will have: 
• Installed Ubuntu Server
• Configured a working Linux server 
• Produced a deployment guide 
• Created installation documentation 
• Updated their GitHub portfolio 
• Published a LinkedIn learning reflection 

---

## Virtual Machine Specifications

| Feature | Specification |
| :--- | :--- |
| **Hypervisor** | VirtualBox / VMware Workstation / KVM |
| **Guest OS** | Ubuntu 22.04 LTS (or specified distro) |
| **vCPUs Assigned** | 2 Cores |
| **RAM Allocated** | 4 GB (4096 MB) |
| **Virtual Disk Size** | 20 GB (Dynamically Allocated) |
| **Firmware Type** | UEFI (or Legacy BIOS) |
| **Network Adapter** | NAT / Bridged |

---

## Installation Summary
1. **Hypervisor Setup:** Installed and configured the virtualization engine.
2. **ISO Download:** Provisioned the official installation ISO image and verified its SHA-256 checksum.
3. **VM Creation:** Configured system resources according to specifications (RAM, CPU, and Disk).
4. **OS Installation:** 
   * Configured storage partitioning schema (GPT/EFI System Partition).
   * Created standard user account with `sudo` privileges.
   * Completed core package installation and rebooted into the guest system.

---

## Configuration Summary
* **Package Updates:** Executed `sudo apt update && sudo apt upgrade -y` to bring system packages up to date.
* **Guest Additions / Tools:** Installed hypervisor integrations for shared clipboard and display auto-resizing.
* **Network Configuration:** Configured static/DHCP IP settings and verified internet connectivity via `ping`.
* **SSH Access:** Enabled OpenSSH server (`sudo systemctl enable --now ssh`) for remote shell access.

---

## Verification Results
Below are terminal commands executed to verify system setup along with expected outputs:

* **Kernel & Architecture Check:**
  ```bash
  uname -a
  # Output: Linux ubuntu-vm 5.15.0-88-generic #98-Ubuntu SMP x86_64