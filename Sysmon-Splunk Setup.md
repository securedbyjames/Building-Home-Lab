<h1>Setting up Sysmon and Splunk</h1>

<h2>Description</h2>

After researching popoular SIEMs that are commonly used in SOC environments, I learned that Splunk is among the most popular.
Therefore, my goal is to learn SPL (Search Processing Language) and increase my efficiency of searching through logs in Splunk.
After completing the Sysmon labs in TryHackMe, I also understand the importance of first understand windows event logs as those are forwarded to Splunk. I am utilizing
the Swift Security Config within Sysmon, and have added the Event IDs associated with that config along with other important Event IDs in my Cybersecurity Guide. Since my
Macbook has the ARM64 architecture and is not supported by Splunk, I installed sysmon and am running Splunk via my HP Windows Laptop. This allows me to add an additional
computer to my home lab, practice vulnerability testing via Kali Linux on my VM, and analyze the logs via Splunk. I have documented the process of installing Sysmon and
Splunk below.

<h2>Setup</h2>

<p align="left">
Step one was downloading Sysmon from Microsoft, extracting the files to "C:\Sysmon" and running "Sysmon64.exe". Afterwards, I downloaded the Swift Security config from github and installed it in order to reduce the noise
of unwanted event logs and focus on the important ones.
</p>

<p align="center">Confirms Swift Security Config
<br><br>
<img src="https://i.imgur.com/palfijD.png" height="80%" width="80%">
<br />
<br />
</p>

<p align="center">Confirms Sysmon is receiving logs
<br><br>
<img src="https://i.imgur.com/H67uf42.png" height="80%" width="80%">
<br />
<br />
</p>

<p>After downloading and installing Splunk, I had an issue where Splunk was not receiving logs from Sysmon. After researching the topic, I found a solution that worked which involved creating an "inputs.conf" file in notepad and saving it to the proper Splunk Directory. I completed this by opening notepad as an administrator, adding the code to the doc, choosing File > Save as, navigating to the proper directory, and saving the file as "inputs.conf".</p>

<p align="center">Getting data from Sysmon to Splunk
<br><br>
<img src="https://i.imgur.com/j1VaJIY.png" height="80%" width="80%">
<br />
<br />
</p>

<p>After creating a new index called "Sysmon" (as noted in the "inputs.conf" file), I was now able to see the data in Splunk. I also installed the Splunk Add-on for Sysmon. I also confirmed the Swift Security Config was active as represented by the screenshot below (EventIDs correspond with the config).</p>

<p align="center">Receiving the right data from Sysmon
<br><br>
<img src="https://i.imgur.com/ja4AcqT.png" height="80%" width="80%">
<br />
<br />
</p>




