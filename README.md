<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />


<h2>Video Demonstration</h2>

- ### [YouTube: Azure Virtual Machines, Wireshark, and Network Security Groups](https://www.youtube.com)

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
<h2> Infrastucvture Setup </h2>
- Create a Resource Group in Azure to hold resources
- Setup a Virtual Network (Vnet) and Subnet for VM connectivity
- Deploy Two Virtual Machines: One Windows One Linux, both in the same VNet/subnet
- Attach Network Security Groups (NSGs) Default firewall setup for each VM

<h2> Networking Activities & Protocols </h2>
-Test Connectiviity between the VM's by pinging and using other tools. 
Modify Network Security Groups:Open/close ports and observe changes in network behavior 
Experiment with Protocols: Try Services (HTTP,RDP,SSH) and see how firewall rules affect access

<h2> Advanced Experiments & Intuition building </h2>
-Further explore Protocols/Ports: Use different protocols and tools to understand traffic flow
Monitor and Analyze Traffic: Examine what happens at the firewall and network level
-Clean up Resources: Stop or delete VM's to prevent unnecessary Azure charges 

<h2>Actions and Observations</h2>

Start both Azure VM's ; (Windows and Linux private IP's 
<img width="1890" height="881" alt="Screenshot 2025-08-10 at 5 31 22 PM" src="https://github.com/user-attachments/assets/497b9178-c0d3-4f0c-a784-49b6056a5afd" />
<img width="1890" height="881" alt="Screenshot 2025-08-10 at 5 31 22 PM" src="https://github.com/user-attachments/assets/497b9178-c0d3-4f0c-a784-49b6056a5afd" />

RDP into Windows VM open Wireshark and start capture 

From Windows ping to Linux private IP
<img width="1910" height="1017" alt="Screenshot 2025-08-06 at 7 45 58 PM" src="https://github.com/user-attachments/assets/41b05ebe-02e2-4506-b22b-8ab2214f5edd" />

<img width="1914" height="1023" alt="Screenshot 2025-08-06 at 9 56 00 PM" src="https://github.com/user-attachments/assets/6f812b2a-c368-45da-8f63-6164f707bf70" />


<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br /># azure-network-protocols
