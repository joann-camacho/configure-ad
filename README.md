<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (22H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Step 1: Setup Domain Controller in Azure.
- Step 2: Set the Domain Controller’s NIC Private IP address to be static. Log into the VM and disable the Windows Firewall (for testing connectivity)
- Step 3: Setup Client-1 in Azure.
- Step 4: Set Client-1’s DNS settings to DC-1’s Private IP address.
- Step 5: Login to Client-1 VM. Attempt to ping DC-1’s private IP address.
- Step 6: From Client-1, open PowerShell and run ipconfig /all. The output for the DNS settings should show DC-1’s private IP Address.


<h2>Deployment and Configuration Steps</h2>

<p>

![image](https://github.com/user-attachments/assets/a080ad6e-bcf8-4145-89b1-830ca407858a)
  
![image](https://github.com/user-attachments/assets/e145e263-84fd-441e-bf3a-68a83a415a57)
</p>
<p>
Step 1: Setup Domain Controller in Azure:
  Create a Resource Group. Create a Virtual Network and Subnet. Create the Domain Controller VM (Windows Server 2022) named “Domain-Controller-1”

</p>
<br />

<p>
  
![image](https://github.com/user-attachments/assets/128e3cde-c9c1-488e-a318-ae294fd2ef39)

![image](https://github.com/user-attachments/assets/9808c0da-bafa-403a-bbf9-94f819d5e732)
  
</p>
<p>
Step 2: Set the Domain Controller’s NIC Private IP address to be static. Log into the VM and disable the Windows Firewall (for testing connectivity)
</p>
<br />

<p>
  
![image](https://github.com/user-attachments/assets/b481f5e0-242c-4fe3-a8f8-308d29c4ac3d)
</p>
<p>
Step 3: Setup Client-1 in Azure: Create the Client VM (Windows 10) named “Client-1”. (Attach it to the same region and Virtual Network as DC-1.)
</p>
<br />

<p>
  
![image](https://github.com/user-attachments/assets/df9963e8-3b97-412d-b066-6b265e913632)
</p>
<p>
Step 4: Set Client-1’s DNS settings to DC-1’s Private IP address.
</p>
<br />

<p>

![image](https://github.com/user-attachments/assets/816c2a39-2e71-4118-996f-3071a3145d92)
  
</p>
<p>
Step 5: Login to Client-1 VM. Attempt to ping DC-1’s (10.0.0.4) private IP address.
</p>
<br />

<p>
  
![image](https://github.com/user-attachments/assets/04e1f490-a230-4d23-9fb3-d300200e90ae)
</p>
<p>
Step 6: From Client-1, open PowerShell and run ipconfig /all. The output for the DNS settings should show DC-1’s private IP Address.
</p>
<br />
