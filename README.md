<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Creating 2 Virtual Machines in Azure
- Connecting to the Microsoft VM with Remote Desktop
- Installing Wireshark
- Examining different protocols and Network Security Groups

<h2>Actions and Observations</h2>

<p>
This first screenshot in Microsoft Azure is where I created 2 Virtual Machines.
<img src="https://i.imgur.com/KjnQb9e.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/wOaH2tD.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Here is where I connected to the Windows 10 VM using a Remote Desktop connection.
<img src="https://i.imgur.com/pmUSi1h.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
Inside the Windows VM I then downloaded Wireshark, which is a protocol traffic analyzer.
<img src="https://i.imgur.com/UC8GOhN.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
I first filtered for ICMP traffic and then used a ping command in powershell to test network connectivity to the Ubuntu VM and Internet by pinging Google.
<img src="https://i.imgur.com/GjDEmYo.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
These two screenshots are of me experimenting with the Network Security Groups of the Ubuntu VM. I disabled incoming ICMP traffic on the firewall of the Ubuntu VM so that the Windows VM cound not receive any ping reply. I then immediately allowed the ICMP traffic 
<img src="https://i.imgur.com/hHlzG1W.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/FiDYULG.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Filtered for SSH traffic. I spawned the command line for the Ubuntu VM. I tested it by using the Linux commands "uname -a" and "pwd".
<img src="https://i.imgur.com/WDXMHDY.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
Filtered for DHCP traffic. I used the ipconfig /renew command to issue the VM a new IP address.
<img src="https://i.imgur.com/RjmwWON.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
Filtered for DNS traffic. I viewed the IP addresses of www.google.com and disney.com in powershell by using the "nslookup" command.
<img src="https://i.imgur.com/MOpzW8k.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
The last protocol traffic I viewed was RDP. You can't tell by the picture but the traffic was continously moving since the connection is live from my physical laptop to the Windows 10 VM.
<img src="https://i.imgur.com/OssWwDo.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
