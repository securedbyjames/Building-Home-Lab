<h1>Project 2: Controlled Breach: Opening a Hole on Purpose</h1>

<h3>Attack</h3>

<h3>Lab Setup</h3>

- Windows server: 192.168.1.2
- Kali Linux: 192.168.20.11 (VLAN 20)
- Windows 11: 192.168.10.11 (VLAN 10)
- pfSense: Routing + Firewall

<h3>Purpose</h3>
<p>From a security engineer standpoint focusing on north/south traffic in addition to east/west traffic, VLAN segmentation is important. Users from VLAN20 should only be granted specific permissions based on least privilege regarding access to other VLANs. In this lab, one scenario (Scenario 1) includes a misconfiguration where VLAN20 is allowed to access port 20 in VLAN10. In another scenario (Scenario 2), port 445 is blocked from VLAN20 to VLAN10.

<h3>Attack</h3>

- From Kali
    - nmap scan on port 445 simulating SMB enumeration
    - (nmap -p 445,3389) note: lab focuses on 445

<h3>Scenario 1 (Misconfiguration)</h3>

Users in VLAN20 are able to run an nmap scan on VLAN10 (port 445) which should NOT be allowed.

<p align="left">
<img src="https://i.imgur.com/lJ9bKfV.png" height="50%" width=50%"/>

<p align="left">
<img src="https://i.imgur.com/3AKb5Sx.png" height="50%" width="50%"/>

<h3>Scenario 2 (Proper configuration)</h3>

The firewall blocks VLAN20 from running an nmpa scan on VLAN10 (port 445).

<p align="left">
<img src="https://i.imgur.com/k0rDXKE.png" height="50%" width=50%"/>

<p align="left">
<img src="https://i.imgur.com/NIaRJPb.png" height="50%" width="50%"/>
