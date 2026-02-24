<h1>Project 1: VLAN Segmentation & Lateral Movement Prevention</h1>

<h3>Lab Setup</h3>

- Windows server: 192.168.1.2
- Kali Linux: 192.168.20.11 (VLAN 20)
- Windows 11: 192.168.10.11 (VLAN 10)
- pfSense: Routing + Firewall

<h3>Attack</h3>

- Scan with nmap

<p align="left">
<img src="https://i.imgur.com/vfFaQey.png" height="75%" width="75%"/>

<h3>Defense</h3>

- pfSense Firewall denies VLAN 20 access to VLAN 10

<p align="left">
<img src="https://i.imgur.com/HTQe6eZ.png" height="75%" width="75%"/>

<h3>Summary</h3>
