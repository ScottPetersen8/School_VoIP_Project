
# Virtual Setup: FreePBX on Hyper-V

This guide documents the process of setting up FreePBX in a virtual environment using Hyper-V. It includes steps for creating the virtual machine, installing FreePBX, configuring network settings, and accessing the FreePBX GUI.

---

## 🖥️ Creating the Virtual Machine

1. Open **Hyper-V Manager**.
2. Click **New > Virtual Machine**.
3. Name the VM (e.g., `FreePBX-Test`).
4. Choose Generation 1
5. Assign memory (recommended: 2048 MB or more).
6. Configure networking:
   - Connect to an existing virtual switch.
7. Create a virtual hard disk (100 GB ideal).
8. Choose **Install an operating system from bootable image**:
   - Select the FreePBX ISO file(The most recent update, older version of Asterisk behave differently).

📸 <img width="550" height="415" alt="image" src="https://github.com/user-attachments/assets/b366d1d8-f268-40b2-bb5e-656b63ca7b89" />


---

## 💿 Installing FreePBX

1. Start the VM.
2. Follow the on-screen instructions to install FreePBX.
3. Choose FreePBX "PUB" installation (Seeing as the server will live on premesis, FOG works better with installations functioning on the cloud).
4. Choose default options unless customization is needed.
5. When it asks to "WIPE MY DISKS AND INSTALL". Choose the option without serial or test, just the default.
6. Set root password when prompted.

📸 <img width="401" height="295" alt="image" src="https://github.com/user-attachments/assets/c17a9f80-6b92-432b-b3ff-4a653471c017" />


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

📸 <img width="518" height="395" alt="image" src="https://github.com/user-attachments/assets/e4b53b07-150f-4c4c-a33b-cc6c2b8d717c" />



---

## 🧭 Accessing the FreePBX GUI

1. Open a browser on a device in the same network.
2. Navigate to your given IP address of the server that:
   ```
   http://192.168.1.100
   ```
   Command: ip a , will show the IP address of the FreePBX server. 
3. Complete the initial setup wizard which will prompt you to create a username and password. This will be under FreePBX Administration.

📸 <img width="953" height="442" alt="image" src="https://github.com/user-attachments/assets/94d01510-776b-4221-8d04-4dbc5058dae4" />


---

## 📝 Notes

- Ensure the VM has internet access if you plan to install updates.
- Use DHCP reservation or static IP to avoid IP changes.
- Document the root and admin credentials securely.

