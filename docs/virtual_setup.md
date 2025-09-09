
# Virtual Setup: FreePBX on Hyper-V

This guide documents the process of setting up FreePBX in a virtual environment using Hyper-V. It includes steps for creating the virtual machine, installing FreePBX, configuring network settings, and accessing the FreePBX GUI.

---

## 🖥️ Creating the Virtual Machine

1. Open **Hyper-V Manager**.
2. Click **New > Virtual Machine**.
3. Name the VM (e.g., `FreePBX-Test`).
4. Assign memory (recommended: 2048 MB or more).
5. Configure networking:
   - Connect to an existing virtual switch.
6. Create a virtual hard disk (20 GB minimum).
7. Choose **Install an operating system from bootable image**:
   - Select the FreePBX ISO file.

📸 *Insert screenshot of VM creation wizard here*

---

## 💿 Installing FreePBX

1. Start the VM.
2. Follow the on-screen instructions to install FreePBX.
3. Choose default options unless customization is needed.
4. Set root password when prompted.

📸 *Insert screenshot of installation progress here*

---

## 🌐 Configuring Network Settings

1. After installation, log into the Linux shell.
2. Set a static IP address:
   ```bash
   sudo nano /etc/sysconfig/network-scripts/ifcfg-<interface>
   ```
   Example configuration:
   ```
   BOOTPROTO=none
   IPADDR=192.168.1.100
   NETMASK=255.255.255.0
   GATEWAY=192.168.1.1
   DNS1=8.8.8.8
   ONBOOT=yes
   ```
3. Restart the network:
   ```bash
   sudo systemctl restart network
   ```

📸 *Insert screenshot of terminal with IP config here*

---

## 🧭 Accessing the FreePBX GUI

1. Open a browser on a device in the same network.
2. Navigate to:
   ```
   http://192.168.1.100
   ```
3. Complete the initial setup wizard.

📸 *Insert screenshot of FreePBX GUI login page here*

---

## 📝 Notes

- Ensure the VM has internet access if you plan to install updates.
- Use DHCP reservation or static IP to avoid IP changes.
- Document the root and admin credentials securely.

