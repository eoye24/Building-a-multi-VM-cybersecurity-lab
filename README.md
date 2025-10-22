# Setting Up a Cybersecurity Home Lab

## 1.0 Overview

This guide outlines the process of establishing a virtual cybersecurity home lab using **VirtualBox** on a single host laptop. The objective is to create a secure, isolated environment for exploring cybersecurity tools, testing configurations, and practicing network defense skills without compromising the main system.

The lab consists of:
- One **Windows Server** acting as the domain controller.
- Two **Windows 8** client machines.
- An internal virtual network connecting all systems.

Once configured, this lab enables simulation of real-world security scenarios, including:
- User authentication
- Group policies
- Endpoint security
- Malware containment
- Penetration testing

### Lab Specifications
- **Host Machine**: Laptop with 64GB RAM
- **Hypervisor**: VirtualBox
- **Operating Systems**: ISO files for Windows Server and Windows 8
- **Storage**: 725GB free disk space

---

## 2.0 Installation of VirtualBox

1. **Download VirtualBox**:
   - Visit the official VirtualBox website (https://www.virtualbox.org/).
   - Download the latest version compatible with your host laptop’s operating system.
   - Install the VirtualBox Extension Pack for additional features like USB support.

2. **Install VirtualBox**:
   - Run the installer and follow the on-screen prompts.
   - Ensure the installation includes network adapters for virtual networking.
   - Verify installation by launching VirtualBox and checking for errors.

---

## 3.0 Installing Windows Server Operating System on VirtualBox

1. **Obtain Windows Server ISO**:
   - Download a legitimate Windows Server ISO (e.g., Windows Server 2019 or 2022) from Microsoft’s official website.

2. **Create a New Virtual Machine**:
   - Open VirtualBox and click **New**.
   - Name the VM.
   - Select **Microsoft Windows** as the type and choose the appropriate Windows Server version.
   - Allocate resources based on host machine’s capacity:
     - RAM: 4-8GB (adjust based on available host RAM).
     - CPU: 2-4 cores.
     - Storage: 100-200GB dynamic virtual hard disk.

3. **Configure VM Settings**:
   - Mount the Windows Server ISO in the VM’s optical drive.
   - In this setup, I changed the network adapter to **Bridged Network**.

4. **Installation of Windows Server**:
   - Start the VM and follow the Windows Server installation prompts.
   - Choose the **Standard** edition for this project.
   - I configure the administrator password and complete the setup.

5. **Set Up Domain Controller**:
   - Install Active Directory Domain Services (AD DS) via Server Manager.
   - Promote the server to a domain controller by configuring a new domain (e.g., `techouse.io`).
   - Verify domain functionality using tools like `nslookup`.

---

## 4.0 Installation of Two Client PCs Running Windows 8 on VirtualBox

1. **Obtain Windows 8 ISO**:
   - Download a legitimate Windows 8 ISO from Microsoft or an authorized source.

2. **Create Two Virtual Machines**:
   - For each client (e.g., "Win8_PC1" and "Win8_PC2"):
     - Create a new VM in VirtualBox.
     - Select **Microsoft Windows** and **Windows 8 (64-bit)**.
     - Allocate resources:
       - RAM: 2-4GB per client.
       - CPU: 1-2 cores.
       - Storage: 50-100GB dynamic virtual hard disk.

3. **Configure VM Settings**:
   - Mount the Windows 8 ISO in each VM’s optical drive.

4. **Install Windows 8**:
   - Start each VM and follow the Windows 8 installation prompts.
   - Set up user accounts and configure basic settings.

5. **Join Clients to the Domain**:
   - On each Windows 8 client, navigate to **System Properties** > **Computer Name** > **Change**.
   - Join the domain (e.g., `techouse.io`) using credentials from the Windows Server domain controller.
   - Reboot the clients and verify domain connectivity by logging in with a domain account.

---

## 5.0 Conclusion

The virtual cybersecurity lab is now fully operational, consisting of a **Windows Server** domain controller and two **Windows 8** client machines communicating within a secure, isolated internal network. This setup allows for experimentation with:
- Domain management
- User authentication
- Group policies
- Basic security configurations

### Next Steps
The lab can be expanded by:
- Adding Linux-based virtual machines for cross-platform testing.
- Incorporating firewalls (e.g., pfSense) for network security simulations.
- Introducing intentionally vulnerable systems (e.g., Metasploitable) for penetration testing practice.

This environment provides a robust platform for honing cybersecurity skills in a controlled setting, ideal for learning and experimentation.

---

**Author**: Oyewale Akinwotu 
