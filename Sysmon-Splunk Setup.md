<h1>Setting up Sysmon and Splunk</h1>

<h2>Description</h2>

After researching popoular SIEMs that are commonly used in SOC environments, I learned that Splunk is among the most popular.
Therefore, my goal is to learn SPL (Search Processing Language) and increase my efficiency of searching through logs in Splunk.
After completing the Sysmon labs in TryHackMe, I also understand the importance of first understand windows event logs as those are forwarded to Splunk. I am utilizing
the Swift Security Config within Sysmon, and have added the Event IDs associated with that config along with other important Event IDs in my Cybersecurity Guide. Since my
Macbook has the ARM64 architecture and is not supported by Splunk, I installed sysmon and am running Splunk via my HP Windows Laptop. This allows me to add an additional
computer to my home lab, practice vulnerability testing via Kali Linux on my VM, and analyze the logs via Splunk. I have documented the process of installing Sysmon and
Splunk below.

<h3>Setup</h3>

