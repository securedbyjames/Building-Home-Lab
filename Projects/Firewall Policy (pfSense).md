<h1>Firewall Policy for Virtual Home Lab</h1>

<h2>Security Objectives</h2>

- Prevent VLAN spoofing
- Block east-west lateral movement
- Allow controlled internet access
- Restrict DNS to internal resolver
- Restrict DHCP to server
- Prevent unauthorized cross-VLAN access
- Used floating rules for to apply one rule to multipe VLANs to enforce a consistent policy, reduce misconfiguration, and centralize enforcement.

<h2>Default Deny Model</h2>

- No implicit trust between VLANs
- Explicitly allow only required services
- Block everything else

<b>Rules explained from top to bottom</b>

<p align="left">
<img src="https://i.imgur.com/z3rdXye.png" height="100%" width=100%"/>

1. Prevents traffic from claiming it's from an internal VLAN range to mitigate spoofing attacks
2. East-west traffic is dnied unless it's required and allow rules apply
3. Allows outbound web traffic
4. Allows encrypted outbound web traffic
5. Forces all VLAN clients to use internal DNS server
   - Forcing DNS through a controlled server allows monitoring and logging of DNS queries.
6. Allows clients to recieve IP addresses

<h2>Order of Rules</h2>

- Anti-spoofing rule first
- Block inter-VLAN rule second
- Allow necessary services below
- Implicit deny at bottom
- (Firewall rules are processed top-down. Specific allow rules must appear below global block rules and be carefully ordered to avoid unintended access.)

<h2>Summary</h2>
Implemented VLAN segmentation using pfSense floating rules. Enforced anti-spoofing, blocked east-west traffic, restricted DNS to internal resolver, and limited outbound traffic to required web services following a least-privilege model.
