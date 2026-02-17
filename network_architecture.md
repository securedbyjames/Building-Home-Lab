<h1>Network Architecture</h1>

<h2>Logical Topology</h2>

<h2>IP Addressing</h2>

<b>Overview</b>
- LAN subnet: 192.168.1.0/24
- pfSense LAN & Default Gateway: 192.168.1.1
- Windows Server: 192.168.1.2
- Windows 11: DHCP
- Kali Linux: DHCP
  
<b>DHCP</b>
  - Excluded: 192.168.1.1 - 192.168.1.10
  - Available: 192.168.1.11 - 192.168.1.255
