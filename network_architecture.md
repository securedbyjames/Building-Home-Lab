<h1>Network Architecture</h1>

<h2>Logical Topology</h2>

<h2>IP Addressing</h2>

<b>Overview</b>
- LAN subnet: 192.168.1.0/24
- pfSense LAN & Default Gateway: 192.168.1.1
- Windows Server: 192.168.1.2
- Windows 11: DHCP
- Kali Linux: DHCP

<b>VLANs</b>
- VLAN 10 (Users)
  - Subnet: 192.168.10.0
  - Default Gateway: 192.168.10.1
- VLAN 20 (Kali)
  - Subnet: 192.168.20.0
  - Default Gateway: 192.168.20.1
- VLAN 30 (DMZ)
  - Subnet: 192.168.30.0
  - Default Gateway: 192.168.30.1
  
<b>DHCP</b>
  - Excluded: 192.168.1.1 - 192.168.1.10
  - Available: 192.168.1.11 - 192.168.1.255

