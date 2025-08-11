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
Setup,RDP,baseline ICMP

Start both Azure VM's ; (Windows and Linux private IP's)
<img width="1890" height="881" alt="Screenshot 2025-08-10 at 5 31 22 PM" src="https://github.com/user-attachments/assets/497b9178-c0d3-4f0c-a784-49b6056a5afd" />
<img width="1890" height="881" alt="Screenshot 2025-08-10 at 5 31 22 PM" src="https://github.com/user-attachments/assets/497b9178-c0d3-4f0c-a784-49b6056a5afd" />

RDP into Windows VM open Wireshark and start capture 

From Windows ping to Linux private IP
<img width="1910" height="1017" alt="Screenshot 2025-08-06 at 7 45 58 PM" src="https://github.com/user-attachments/assets/41b05ebe-02e2-4506-b22b-8ab2214f5edd" />

<img width="1914" height="1023" alt="Screenshot 2025-08-06 at 9 56 00 PM" src="https://github.com/user-attachments/assets/6f812b2a-c368-45da-8f63-6164f707bf70" />

In the Linux VM's NSG, add a deny rule for inbound ICMP;test ping fails
Change/disable the rule or add allow ICMP test ping
<img width="1000" height="911" alt="Screenshot 2025-08-06 at 10 05 06 PM" src="https://github.com/user-attachments/assets/22d7011a-2db1-4fa7-9920-48f3ceedc950" />
<img width="1879" height="794" alt="Screenshot 2025-08-10 at 6 33 34 PM" src="https://github.com/user-attachments/assets/41ff99b0-7c41-434d-8a93-0a672a9f4320" />


SSH (TCP 22) 
From Windows VM:ssh labuser@<linux private IP> aunthentiate;run id, hostname, unamae -a exit
<img width="1910" height="1026" alt="Screenshot 2025-08-10 at 6 54 01 PM" src="https://github.com/user-attachments/assets/f8e33617-1e45-4471-b901-8483ac5f5b2c" />
<img width="980" height="589" alt="Screenshot 2025-08-10 at 7 35 56 PM" src="https://github.com/user-attachments/assets/28de3084-3cbf-4765-a7bd-7bde78413f1c" />


DHCP (UDP 67/68) 
<img width="1890" height="832" alt="Screenshot 2025-08-10 at 8 13 32 PM" src="https://github.com/user-attachments/assets/c6389f0f-d53d-4a4c-b87e-2b5108fe41f2" />
<img width="1586" height="220" alt="Screenshot 2025-08-10 at 8 15 38 PM" src="https://github.com/user-attachments/assets/d9b00513-8bda-48e7-9082-4e58c26c6e4a" />
<img width="1890" height="832" alt="Screenshot 2025-08-10 at 8 13 32 PM" src="https://github.com/user-attachments/assets/551ed5b8-60e8-4c85-bc8c-b94628abd4aa" />


DNS (UDP/TCP 53) Filter DNS or udp.port==53, Run nslookup

<img width="839" height="191" alt="Screenshot 2025-08-10 at 8 21 04 PM" src="https://github.com/user-attachments/assets/7bb7f288-1558-4b60-bd22-ffa7be012c82" />
<img width="839" height="191" alt="Screenshot 2025-08-10 at 8 21 04 PM" src="https://github.com/user-attachments/assets/49f0e23f-1fa0-4149-a06e-ddf02a83bdd7" />


RDP (TCP 3389) Wireshark: Filter tcp.port==3389 during live RDP session
<img width="1784" height="649" alt="Screenshot 2025-08-10 at 8 28 39 PM" src="https://github.com/user-attachments/assets/d771b892-a762-4883-a6b2-e83c29e993f9" />

Delete the resource groups in Azure 
<img width="1075" height="818" alt="Screenshot 2025-08-10 at 8 31 20 PM" src="https://github.com/user-attachments/assets/9f0280a1-4a11-4875-8c2d-694f0291f987" />


<br /># azure-network-protocols
