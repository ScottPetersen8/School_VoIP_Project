# FreePBX Physical Setup Documentation

## Overview

This document outlines the physical deployment of FreePBX for internal VoIP communication at the school. It includes hardware details, network topology, configuration steps, and testing results.

---

## Hardware Components

- **FreePBX Server**: Dell desktop (physical install)
- **VoIP Phones**: Yealink T40G (x3)
- **Network Switch**: HP ProCurve 1410-24G (Managed)
- **Router**: School's existing LAN router
- **Other Devices**: Laptops for GUI access and testing

---

## Network Topology

- All devices are connected via Ethernet.
- Phones and server are on the same subnet.
- DHCP provided by the router.

---

## FreePBX Installation

- **Method**: ISO install on physical desktop
- **Access**: Web GUI available from other devices on LAN
- **Admin Login**: Set during initial setup
- **Shell Access**: Available via physical console

---

## Switch Configuration (HP ProCurve 1410-24G)

- **Mode**: Managed
- **VLANs**: Not configured (default VLAN used)
- **QoS**: Optional for VoIP prioritization
- **Port Setup**:
  - Port 1: FreePBX Server
  - Port 2-4: Yealink Phones
  - Port 5: Admin Laptop

---

## Phone Setup (Yealink T40G)

- **Registration**: Successfully registered with FreePBX
- **Extensions**: Assigned via GUI
- **Features**:
  - Internal calling
  - Voicemail
  - Clear audio quality

---

## Call Recording

- **Status**: Enabled for internal calls
- **Method**: Configured via FreePBX GUI
- **Storage**: Local disk on FreePBX server

---

## Testing & Results

- ✅ Phones can call each other
- ✅ Voicemail works
- ✅ Call recording functional
- ✅ GUI accessible from LAN
- ✅ Audio quality confirmed

---

## Next Steps

- [ ] Document VLAN setup if implemented
- [ ] Explore external call routing (if needed)
- [ ] Backup configuration
- [ ] Push documentation to GitHub

---

## GitHub Repository

> _Link to be added once uploaded_

---

## Notes

- This setup is part of a school VoIP project.
- Designed for internal communication only.
- Future upgrades may include virtual hosting or SIP trunking.