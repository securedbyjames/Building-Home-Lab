<h1>Active Directory Enterprise Deployment</h1>

<h2>Overview</h2>
'SPIDERMAN' serves as the domain controller, DNS, and DHCP server for this lab environment. All clients use SPIDERMAN as their primary DNS server, and destination to receive IP addresses (unless set to a static IP address).

<h3>Domain</h3>

- securedbyjames.com

<h3>Roles</h3>

  - Active Directory Domain Services
  - DNS
  - DHCP

<h3>Orginizational Structure</h3>
I am utilizing the AGDLP method for my OU structure to keep permissions secure and organized.<br><br>

  - A: Accounts
  - G: Global Groups
  - DL: Domain Local Groups
  - P: Permissions

<p align="left">
<img src="https://i.imgur.com/1CrR9sF.png" height="75%" width="75%"/>

Accounts represent users, and are not given permissions directly. Global groups represent job roles in which users are placed in according to job function or department. Domain Local Groups represent access to specific resources, and permissions are assigned to domain local groups only. To ensure users have the correct permissions based on job role, global groups are placed inside domain local groups.

<b>Benefits of AGDLP Structure</b>
  - Least privilege access by assigning only required permissions
  - Centralized access control through group membership
  - Simplified administration when onboarding or offboarding users
  - Scalability in larger environments with many resources

<b>IT Share Folder Permissions Example</b>
IT_ShareFolder_R Group: The 'R' represents read, and provides any global group (Help Desk and IT Technicians) read access to this folder. The global group for those job roles are members of this domain local group.

<p align="left">
<img src="https://i.imgur.com/OZChpAB.png"/>


<h2>DNS Configuration</h2>

DNS was installed automatically with Active Directory Domain Services was configured on the server.

<b>Forward Lookup Zones</b><br>
Stores host records that map hostnames to IP addresses

<p align="left">
<img src="https://i.imgur.com/YCVSJzl.png" height="75%" width="75%"/>

<b>Reverse Lookup Zones</b><br>
Used for logging, troubleshooting, and security.

<p align="left">
<img src="https://i.imgur.com/fUh2OQj.png" height="75%" width="75%"/>

<b>Forwarders</b><br>
Allows clients to resolve internet domain domains.

<p align="left">
<img src="https://i.imgur.com/0JWy9iD.png" height="75%" width="75%"/>

Active Directory uses DNS to locate domain services through SRV records. Domain-joined clients query DNS to locate domain controllers, Kerberos authentication services, and LDAP directory services.

Confirmed DNS is working properly using nslookup commands pointing to an IP address, and domain name.
<p align="left">
<img src="https://i.imgur.com/LKBzG6o.png" height="75%" width="75%"/>

<h2>DHCP</h2>

Used when a client connects to the network and needs an IP address. The client's device sends a DHCP request and the DHCP server assigns an available IP address from the configured scope along with the appropriate network settings.

Includes:
  - IP Address Range – The pool of IP addresses that can be assigned to clients
  - Subnet Mask – Defines the network boundary
  - Default Gateway – The router used to reach other networks
  - DNS Servers – Used for hostname resolution
  - Lease Duration – The amount of time a device can keep the assigned IP address

| VLAN   | DHCP Range        | Assignment Type  |
| ------ | ----------------- | ---------------- |
| LAN    | 192.168.1.1 - 255  | Static          |
| USER   | 192.168.10.1 – 255 | DHCP            |
| ATTACK | 192.168.20.1 - 255 | DHCP            |
| DMZ    | 192.168.30.1 - 255 | Static          |

<p align="left">
<img src="https://i.imgur.com/uAfDdAD.png" height="75%" width="75%"/>

Confirmed DHCP is working as Windows 11 PC received an IP address based on being a part of VLAN 10.

<p align="left">
<img src="https://i.imgur.com/4aaKNlm.png" height="75%" width="75%"/>

<h2>Skills Demonstrated</h2>

  - Active Directory
  - DNS integration
  - DHCP configuration
  - Domain joining
  - OU design
  - Identity management
