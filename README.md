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

- Part 1 Create a Windows and Linux VM within the same Network
- Step 2
- Step 3
- Step 4

<h2>Create a Windows and Linux VM within the same Network</h2>

![image](https://github.com/user-attachments/assets/99266f53-3cd9-405c-abd8-8cca2b3b0ee8)

<p>
Create a Resource Group
</p>

![image](https://github.com/user-attachments/assets/253a32e3-39ba-47ba-8790-a69b873a3740)

![image](https://github.com/user-attachments/assets/152266a7-02f8-4f6d-8cb7-0ab399f0e805)

<p>
Create a Windows 10 Virtual Machine (VM)
  </p>
Select the previously created Resource Group
</p>
Allow it to create a new Virtual Network (Vnet) and Subnet
</p>

![image](https://github.com/user-attachments/assets/53ba0a83-9cdd-4d0c-b009-a68c2bb35466)

![image](https://github.com/user-attachments/assets/ade3caf8-bbd0-4a94-92c6-885087c677db)

<p>
Create a Linux (Ubuntu) VM
  </p>
Select the previously created Resource Group and Virtual Network—the Virtual Network ‼️MUST BE THE SAME‼️
</p>
Authentication type: Username/Password
</p>


<h2>Install Wireshark and observe ICMP traffic</h2>


![image](https://github.com/user-attachments/assets/dd628ac2-6afa-4613-96d2-98a47715df2e)

<p>
Use Remote Desktop to connect to your Windows 10 Virtual Machine
</p>

![image](https://github.com/user-attachments/assets/e4c33811-b4bf-4f6a-b14b-12343fe1574e)

<p>
Within your Windows 10 Virtual Machine, Install Wireshark
</p>

![image](https://github.com/user-attachments/assets/44b8c6f6-2a87-434b-be8a-2e69b2da858c)

<p>
Open Wireshark and start packet capture
</p>

![image](https://github.com/user-attachments/assets/c3f4649a-c51d-474b-88df-e4f87e6df23b)

<p>
Within Wireshark, filter for ICMP traffic only
</p>

![image](https://github.com/user-attachments/assets/ecd54835-92a2-47bd-a2f5-d4fc8954e4b0)

![image](https://github.com/user-attachments/assets/83e9a989-6b30-4a1b-8040-4b057abe8a29)

<p>
Retrieve the private IP address of the Ubuntu VM (linux-vm) and attempt to ping it from within the Windows 10 VM
</p>

![image](https://github.com/user-attachments/assets/799a4c7d-8b38-4b66-a14e-3ba355555f75)

![image](https://github.com/user-attachments/assets/23b703e3-6cbe-4ea6-baf5-24fce511172d)

<p>
Observe ping requests and replies within WireShark
</p>


<h2>Configuring a Firewall [Network Security Group</h2>


<p>
Configuring a Firewall [Network Security Group
</p>


<p>
Lorem ipsum dolor sit amet, 
</p>


<p>
Lorem ipsum dolor sit amet, 
</p>


<p>
Lorem ipsum dolor sit amet, 
</p>


<p>
Lorem ipsum dolor sit amet, 
</p>


<p>
Lorem ipsum dolor sit amet, 
</p>


<p>
Lorem ipsum dolor sit amet, 
</p>


<p>
Lorem ipsum dolor sit amet, 
</p>


<p>
Lorem ipsum dolor sit amet, 
</p>


<p>
Lorem ipsum dolor sit amet, 
</p>


<p>
Lorem ipsum dolor sit amet, 
</p>


<p>
Lorem ipsum dolor sit amet, 
</p>


<p>
Lorem ipsum dolor sit amet, 
</p>


<p>
Lorem ipsum dolor sit amet, 
</p>


<p>
Lorem ipsum dolor sit amet, 
</p>


<p>
Lorem ipsum dolor sit amet, 
</p>


<p>
Lorem ipsum dolor sit amet, 
</p>


<p>
Lorem ipsum dolor sit amet, 
</p>


<p>
Lorem ipsum dolor sit amet, 
</p>


<p>
Lorem ipsum dolor sit amet, 
</p>


<p>
Lorem ipsum dolor sit amet, 
</p>


<p>
Lorem ipsum dolor sit amet, 
</p>


<p>
Lorem ipsum dolor sit amet, 
</p>


<p>
Lorem ipsum dolor sit amet, 
</p>


<p>
Lorem ipsum dolor sit amet, 
</p>


<p>
Lorem ipsum dolor sit amet, 
</p>


<p>
Lorem ipsum dolor sit amet, 
</p>


<p>
Lorem ipsum dolor sit amet, 
</p>


<p>
Lorem ipsum dolor sit amet, 
</p>


<p>
Lorem ipsum dolor sit amet, 
</p>


<p>
Lorem ipsum dolor sit amet, 
</p>


<p>
Lorem ipsum dolor sit amet, 
</p>


<p>
Lorem ipsum dolor sit amet, 
</p>


<p>
Lorem ipsum dolor sit amet, 
</p>


<p>
Lorem ipsum dolor sit amet, 
</p>


<p>
Lorem ipsum dolor sit amet, 
</p>


<p>
Lorem ipsum dolor sit amet, 
</p>


<p>
Lorem ipsum dolor sit amet, 
</p>


<p>
Lorem ipsum dolor sit amet, 
</p>


<p>
Lorem ipsum dolor sit amet, 
</p>


<p>
Lorem ipsum dolor sit amet, 
</p>


<p>
Lorem ipsum dolor sit amet, 
</p>


<p>
Lorem ipsum dolor sit amet, 
</p>


<p>
Lorem ipsum dolor sit amet, 
</p>
