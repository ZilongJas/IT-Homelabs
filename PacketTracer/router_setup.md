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

1. **Access PC1**: 
2. **Open Configuration**: 
3. **Select Interface**: 
   - Choose **FastEthernet0**.  
4. **Assign IPv4 Address**:  
   - **IPv4 Address**: `192.168.10.10`.  
   - **Subnet Mask** will be automatically filled.  
5. **Configure Default Gateway**:  
   - Navigate to **Settings** in the global options.  
   - **Default Gateway**: `192.168.10.1`.  
6. **Repeat for PC2**
   - **Default Gateway**: `192.168.30.1`
   - **IPv4 Address**: `192.168.30.10`

## Configuring Routers

Configure the router for network functionality.

1. **Access the CA Router**: 
2. **Open CLI**:   
3. **Enter Privileged EXEC Mode**: 
    - `enable` 
4. **Enter Configuration Mode**:
    - `configure terminal` 
5. **Change Hostname of Router**:
    - `hostname CA`
6. **Change interface**:
    - `interface g0/1`
7. **Change IP address in the g0/1 interface**:
    - `ip address 192.168.10.1 255.255.255.0`
8. **Turn on router**: 
    - `no shutdown`
9. **Exit g0/1 interface, switch to g0/0 interface**
10. **Change IP address in the g0/0 interface**: 
    - `ip address 192.168.20.1 255.255.255.0`
11. **Turn on router**
12. **Configure NY Router**:
    - Repeat steps 1-11
    - Interface `g0/1` ip address: `192.168.30.1`
    - Interface `g0/0` ip address: `192.168.20.2`
