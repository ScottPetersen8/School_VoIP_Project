# FreePBX Physical Setup Documentation

## Overview

This document outlines the physical deployment test of FreePBX for internal VoIP communication. It includes hardware details, network topology, configuration steps, and testing results.

---

## Hardware Components

- **FreePBX Server**: Dell desktop (physical install)
- **VoIP Phones**: Yealink T40G (x2)
- **Network Switch**: HP ProCurve 1410-24G (unmanaged)
- **Other Devices**: Laptop for GUI access and testing

---

## Network Topology

- All devices are connected via Ethernet.
- Phones and server are on the same subnet.
- DHCP provided by server.

---

## FreePBX Installation

- **Method**: ISO install on physical desktop, via USB
- **Access**: Web GUI available from other devices on LAN and Wi-Fi
- **Admin Login**: Set during initial setup
- **Shell Access**: Available via physical console

---

## Switch Configuration (HP ProCurve 1410-24G)

- **Mode**: Unmanaged
- **QoS**: Optional for VoIP prioritization
- **Port Setup**:
  - Port 1: FreePBX Server
  - Port 2-4: Yealink Phones
  - Port 5: Admin Laptop
  - Port 6: Backbone network connection

---

## Phone Setup (Yealink T40G)

- **Registration**: Successfully registered with FreePBX
- **Extensions**: Assigned via GUI
- **Features**:
  - Internal calling
  - Voicemail
  - Clear audio quality

---

## Testing & Results

- ✅ Phones can call each other
- ✅ Voicemail works
- ✅ GUI accessible from LAN and Wi-Fi(if on the same subnet)
- ✅ Audio quality confirmed

---

## Next Steps

- [ ] Document VLAN setup if implemented
- [ ] Backup configuration
- [ ] Push documentation to GitHub

---

## GitHub Repository

(https://github.com/ScottPetersen8/School_VoIP_Project/tree/main)

---

## Notes

- This setup is part of a school VoIP project.
- Designed for internal communication only.
- Future upgrades may include virtual hosting or SIP trunking.
