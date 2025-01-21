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
- Step 2 Install Wireshark and observe ICMP traffic
- Step 3 Configuring a Firewall (Network Security Group)
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


<h2>Configuring a Firewall (Network Security Group)</h2>

![image](https://github.com/user-attachments/assets/dfe2c86b-f0f3-4324-b817-2fe602778174)

<p>
Initiate a perpetual/non-stop ping from your Windows 10 VM to your Ubuntu VM (ping 10.0.0.5 -t)
</p>

![image](https://github.com/user-attachments/assets/3019ace2-4b2f-4188-8cb9-e99852272729)

![image](https://github.com/user-attachments/assets/4b42e48e-738f-4d3a-8520-6db542fc7936)

<p>
Open the Network Security Group your Ubuntu VM is using, create a new inbound rule and disable incoming (inbound) ICMP traffic
</p>

![image](https://github.com/user-attachments/assets/7da46811-afeb-4974-af22-7f43afd7eec5)

<p>
Back in the Windows 10 VM, observe the ICMP traffic in WireShark and the command line Ping activity
</p>

![image](https://github.com/user-attachments/assets/9328ad6a-8078-4be3-ab9f-b2e11330b507)

<p>
Re-enable ICMP traffic for the Network Security Group your Ubuntu VM is
</p>

![image](https://github.com/user-attachments/assets/1379d4df-3b6d-4bc1-a675-116806b65b85)

<p>
Back in the Windows 10 VM, observe the ICMP traffic in WireShark and the command line Ping activity
</p>


<h2>Observe SSH Traffic</h2>


![image](https://github.com/user-attachments/assets/b232af8c-2b6b-45ed-921d-3dd4aab21e89)

<p>
Back in Wireshark, start a packet capture up, Filter for SSH traffic only
</p>

![image](https://github.com/user-attachments/assets/07065b59-c34d-4dd3-8459-c81f3cbdfc7a)

![image](https://github.com/user-attachments/assets/274da6b7-55f2-4055-af23-cef47b87cb4c)

<p>
From your Windows 10 VM, “SSH into” your Ubuntu Virtual Machine (via its private IP address)
</p>

![image](https://github.com/user-attachments/assets/005b4d01-1c55-4be1-baf0-2d598a35393b)

![image](https://github.com/user-attachments/assets/c475af7b-eac2-4f48-b3e4-4f42f62528c3)

![image](https://github.com/user-attachments/assets/1ff8ec33-02ea-49f1-88fe-7233daaaa997)

<p>
Type commands (username, pwd, etc) into the linux SSH connection and observe SSH traffic spam in WireShark
</p>

![image](https://github.com/user-attachments/assets/6d543f33-b05d-4f77-a6fc-0bffc65925c2)

<p>
Exit the SSH connection by typing ‘exit’ and pressing [Enter]
</p>


<h2>Observe DHCP Traffic</h2>



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
