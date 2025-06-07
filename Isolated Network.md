<h1>Creating an Isolated Private Network</h1>

<h2>Description</h2>

The purpose of my isolated private network is not only to keep my hardware and data secure, but to also understand the difference between my VM's network adapter settings such as NAT, Bridged, Host-Only, and creating custom networks.
After installing my Kali Linux and Ubuntu Server VMs, I created a private network in order to disable DHCP and internet access so I could freely test vulnerable machines while remaining 100% secure.

<p align="center">
<br />
Configuring Private Network<br/>
<img src="https://i.imgur.com/fIRtxeE.png" height="80%" width="80%">
<br />
<br />

Afterwards, I connected both VMs to the private network "privatenet", configured static ip addresses, and ran a few ping tests to ensure the VMs could communicate with each other.

<p align="center">
<br />
Setting Static IP Address (Kali Linux)<br/>
<img src="https://i.imgur.com/QSi0an1.png[/img]" height="80%" width="80%">
<br />
<br />

<p align="center">
<br />
Setting Static IP Address (Ubuntu Server)<br/>
<img src="https://i.imgur.com/SDqbbAO.png" height="80%" width="80%">
<br />
<br />

<p align="center">
<br />
Pinging Static IP of Ubuntu Server VM<br/>
<img src="https://i.imgur.com/z4LO2Jp.png" height="80%" width="80%">
<br />
<br />

Now the fun begins! I installed the LAMP stack on the Ubuntu server to ensure I could run the vulnerable web apps and databases.
