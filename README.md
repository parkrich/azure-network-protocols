<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
Observing traffic between NSGs and Azure Virtual Machines. <br />

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

- Filter ICMP
- Filter SSH
- Filter DHCP
- Filter DNS
- Filter tcp port 3389

<h2>Actions and Observations</h2>

<p>
Filtering out ICMP traffic in Wireshark using Powershell. A perpetual ping is created from Windows machine to Ubuntu. The traffic between both machines is seen being disabled and then reenabled.
</p>

![image](https://github.com/parkrich/azure-network-protocols/assets/137697108/0bf4409c-5b2a-4ab7-9798-1846204c2193)
<br />

<p>
Signing into Secure Shell to observe the filtering of ssh traffic. This is done by accessing Ubuntu through the private IP address.
</p

 ![image](https://github.com/parkrich/azure-network-protocols/assets/137697108/ac7f45fa-39cd-419f-9113-8c0aeeb6ff18) 
<br />

<p>
Filtering dhcp traffic by renewing, or reissuing, an IP address for the Windows VM.
</p>

![image](https://github.com/parkrich/azure-network-protocols/assets/137697108/1cd8ec97-c6ef-4bd8-a7b8-313535667820)
<br />

<p>
Filtering dns traffic of random websites using nslookup. Notice that one of the websites gives multiple IPv4's as well as multiple IPv6's.
</p>

![image](https://github.com/parkrich/azure-network-protocols/assets/137697108/58d31d89-101a-476c-b95c-72a43a39aebc)
<br />

<p>
Interesting observation of tcp port 3389. The filter creates perpetual traffic as port 3389 is a livestream port, meaning traffic will always flow through it regardless of what is done to it.
</p>

![image](https://github.com/parkrich/azure-network-protocols/assets/137697108/3d0c705e-10c0-4023-a2f0-9f7547ccf60a)
<br />
