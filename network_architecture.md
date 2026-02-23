<h1>Network Architecture</h1>

| VLAN ID | Network Name     | Subnet          | Gateway        | Purpose                |
| ------- | ---------------- | --------------- | -------------- | ---------------------- |
| N/A     | WAN              | DHCP            | ISP / Host NAT | External connectivity  |
| 1       | Management / LAN | 192.168.1.0/24  | 192.168.1.1    | Infrastructure systems |
| 10      | User Network     | 192.168.10.0/24 | 192.168.10.1   | End-user machines      |
| 20      | Attack Network   | 192.168.20.0/24 | 192.168.20.1   | Offensive testing      |
| 30      | DMZ              | 192.168.30.0/24 | 192.168.30.1   | Public-facing services |

<p align="left">
<img src="https://i.imgur.com/ovl1k7n.png" height="50%" width="50%"/>

<h2>Firewall (pfSense)</h2>

| Interface | Type                | IP Addressing  | Description               |
| --------- | ------------------- | -------------- | ------------------------- |
| WAN       | Virtual NIC         | DHCP           | ISP facing interface      |
| LAN       | Virtual NIC (Trunk) | 192.168.1.1/24 | Internal VLAN trunk       |

<p align="left">
<img src="https://i.imgur.com/VHYiVxW.png" height="50%" width="50%"/>

<h2>VLANs</h2>

| Interface | Type                | IP Addressing  | Description               |
| --------- | ------------------- | -------------- | ------------------------- |
| WAN       | Virtual NIC         | DHCP           | Internet-facing interface |
| LAN       | Virtual NIC (Trunk) | 192.168.1.1/24 | Internal VLAN trunk       |

<h2>DHCP</h2>

| VLAN   | DHCP Range        | Assignment Type  |
| ------ | ----------------- | ---------------- |
| LAN    | 192.168.1.1 - 255  | Static          |
| USER   | 192.168.10.1 – 255 | DHCP            |
| ATTACK | 192.168.20.1 - 255 | DHCP            |
| DMZ    | 192.168.30.1 - 255 | Static          |

<p align="left">
<img src="https://i.imgur.com/C7iblRv.png" height="50%" width="50%"/>

<h2>Virtual Switching</h2>

| Component         | Configuration                 |
| ----------------- | ----------------------------- |
| Virtual Switch    | Single trunked virtual switch |
| VLAN Tagging      | Handled by pfSense            |
| VM NIC Assignment | VLAN ID set per VM            |
