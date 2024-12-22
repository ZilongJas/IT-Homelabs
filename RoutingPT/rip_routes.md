## Information about the network

```
CA Router:
G0/0: 192.168.20.1/24
G0/1: 192.168.10.1/24

NY Router:
G0/0: 192.168.20.2/24
G0/1: 192.168.30.1/24

Switches:
CA Switch: Connected to CA Router G0/1 and PC1 via F0/2
NY Switch: Connected to NY Router G0/1 and PC2 via F0/2

End Devices:
PC1: 192.168.10.10/24 (CA side)
PC2: 192.168.30.10/24 (NY side)

Subnets:
CA-NY Link: 192.168.20.0/24
CA LAN: 192.168.10.0/24
NY LAN: 192.168.30.0/24
```

## Visual

![image](https://github.com/user-attachments/assets/b6c749c7-7f62-43b2-a187-62d4a357d100)

## Configuring CA and NY Routers using the RIP route method

1. CA Router
  - `enable`: Privileged EXEC Mode
  - `conf t`: Configuration Mode
  - `router rip`: Enable RIP on router
  - `version 2`: use RIP v2
  - `network 192.168.10.0`: adds the 192.168.10.0/24 network in RIP routing process
  - `network 192.168.20.0`: adds the 192.168.20.0/24 network in RIP routing process
2. NY Router
  - Repeat steps from CA Router with these changes:
  - `network 192.168.20.0`
  - `network 192.168.30.0`
