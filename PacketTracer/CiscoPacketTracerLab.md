# Routing Setup

This section refers to the network diagram shown below:

<img src="https://github.com/user-attachments/assets/db78b45d-b3e3-413e-b444-7942fef0e498" alt="Routing Diagram" width="400">

- Host A communicates with Host B by sending its destination MAC address to the router, rather than Host B's MAC address.
- The router disregards the MAC address but processes the destination IP address. It forwards the packet through the second switch, eventually reaching Host B.

---

## Network Design Overview

This setup demonstrates connectivity between two locations, California (CA) and New York (NY). The topology includes two PCs, two switches, and two routers, as shown below:

<img src="https://github.com/user-attachments/assets/a3daa9e2-8693-4851-8e3e-275dd7bc747e" alt="Network Design" width="400">

- The devices are interconnected using straight-through cables due to the long distance between CA and NY. The third option in Packet Tracer’s cable selection menu is used.

![Cable Selection](https://github.com/user-attachments/assets/293a5262-3cde-40f6-9c3a-e7e333a6d500)

---

## Steps to Connect the Devices

Use the ports specified in the diagram for guidance. Note that the ports are assigned for demonstration purposes and can be adjusted if necessary (e.g., `F0/#`, where `#` represents the port number).

1. Connect `PC1` to `Switch1` using ports `F0/0` (PC1) and `F0/2` (Switch1).
2. Connect `Switch1` to `Router CA` using ports `F0/1` (Switch1) and `F0/1` (Router CA).
3. Connect `PC2` to `Switch2` using ports `F0/0` (PC2) and `F0/2` (Switch2).
4. Connect `Switch2` to `Router NY` using ports `F0/0` (Switch2) and `F0/2` (Router NY).
5. Connect `Router CA` to `Router NY` using ports `G0/0` (Router CA) and `G0/0` (Router NY).

Refer to the following diagram for visual representation:

<img src="https://github.com/user-attachments/assets/0e9da5d0-6e3b-4ff9-9f40-c53e11efde16" alt="Connection Diagram" width="400">

---

## Configuring PCs

Configure PCs within the network to ensure seamless communication and functionality. Refer the diagram for the IP addresses.

1. Click on PC1.
2. Open the **Config** tab.
3. Choose **FastEthernet0** from the interface list.
4. Enter the **IPv4** Address (192.168.10.10). Subnet Mask will automatically be assigned.
5. Choose **Settings** from the global list.
6. Enter the **Default Gateway** (192.168.10.1).
7. Repeat steps 1-6 for PC2. Ensure the **Default Gateway** is updated to reflect the correct address for PC2. 

## Configuring Routers













