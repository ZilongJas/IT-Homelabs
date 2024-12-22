## Network Design Overview

This setup demonstrates connectivity between two locations, California (CA) and New York (NY). The topology includes two PCs, two switches, and two routers, as shown below:

<img src="https://github.com/user-attachments/assets/a3daa9e2-8693-4851-8e3e-275dd7bc747e" alt="Network Design" width="400">

- The devices are interconnected using straight-through cables due to the long distance between CA and NY. 

![Cable Selection](https://github.com/user-attachments/assets/293a5262-3cde-40f6-9c3a-e7e333a6d500)

---

## Connect the Devices

1. Connect `PC1` to `Switch1` using ports `F0/0` (PC1) and `F0/2` (Switch1).
2. Connect `Switch1` to `Router CA` using ports `F0/1` (Switch1) and `F0/1` (Router CA).
3. Connect `PC2` to `Switch2` using ports `F0/0` (PC2) and `F0/2` (Switch2).
4. Connect `Switch2` to `Router NY` using ports `F0/0` (Switch2) and `F0/2` (Router NY).
5. Connect `Router CA` to `Router NY` using ports `G0/0` (Router CA) and `G0/0` (Router NY).

<img src="https://github.com/user-attachments/assets/0e9da5d0-6e3b-4ff9-9f40-c53e11efde16" alt="Connection Diagram" width="400">

---

## Configuring PCs

Configure PCs within the network to ensure seamless communication and functionality.

1. PC1 Configuration:
   - **IPv4 Address**: `192.168.10.10`.
   - **Default Gateway**: `192.168.10.1`. 
2. PC2 Configuration:
   - **IPv4 Address**: `192.168.30.10`
   - **Default Gateway**: `192.168.30.1`

## Configuring Routers

Configure the router for network functionality.

1. CA Router Configuration (CLI):
   - `enable`: Privileged EXEC Mode
   - `conf t`: Configuration Mode
   - `hostname CA`: Change Hostname
   - `interface g0/1`: Change interface
   - `ip address 192.168.10.1 255.255.255.0`: Change IP address
   - `exit`: Exit current interface
   - `interface g0/0`: Switch to g0/0 interface
   - `ip address 192.168.20.1 255.255.255.0`: Change IP address
   - `no shutdown`: Turn on router
     
2. NY Router Configuration (CLI):
   - Repeat steps from CA Router with these changes:
     - Interface: `g0/1` ip address: `192.168.30.1`
     - Interface: `g0/0` ip address: `192.168.20.2`
