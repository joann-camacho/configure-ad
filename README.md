<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell (as an admin)

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (22H2)

<h2>High-Level Deployment and Configuration Steps</h2>

***Prereqs: Create an Azure VM DC-1 (Windows Server 2022) and Create an Azure VM Client-1 (Windows 10 (22H2))***

***A-Record***
- Step 1: Remote Desktop and 'Log into' the DC-1 as your domain admin account (mydomain.com\jane_admin). And also, Log into Client-1 as an admin (mydomain\jane_admin)
- Step 2: From Client-1, Open Powershell (as an admin) and try to (ping “cherry”) and notice that it fails. Type: (Nslookup “mainframe”) and notice that it fails (no DNS record)
- Step 3: Create a DNS A-record on DC-1 for “cherry” and have it point to DC-1’s Private IP address. To (ping "cherry"), 
- Step 4: Go back to Client-1 and try to ping it. Observe that it works.

***Local DNS Cache Exercise***
- Step 1: Go back to DC-1 and change cherry’s record address to 8.8.8.8
- Step 2: Go back to Client-1 and ping “mainframe” again. Observe that it still pings the old address
- Step 3: Observe the local dns cache (ipconfig /displaydns)
- Step 4: Flush the DNS cache (ipconfig /flushdns).
- Step 5: Observe that the cache is empty (ipconfig /displaydns)
- Step 6: Attempt to ping “mainframe” again. Observe the address of the new record is showing up



<h2>Deployment and Configuration Steps</h2>

<p>
<p>
Step 1: Open Remote Desktop and 'Log into' the DC-1 as your domain admin account (mydomain.com\jane_admin). Also, 'Log into' Client-1 as an admin (mydomain\jane_admin)
  
![image](https://github.com/user-attachments/assets/7f8a7d70-c2ac-4d4d-8608-4b95372e4a18)


![image](https://github.com/user-attachments/assets/f07aa873-0ad7-41a4-ac6b-238969b79ff4)

</p>

</p>
<br />

<p>

Step 2: From Client-1, On "Type here to search" located on the bottom left corner next to the 'Windows icon', Type: Powershell. Select: 'run as administrator' and select 'Yes'.

![image](https://github.com/user-attachments/assets/3efc85ac-a7b6-4bb7-a792-45533a528339)

Type: (ping cherry) in PowerShell. Observe that it fails.(This is due to no DNS record)

![image](https://github.com/user-attachments/assets/6e86d39d-687f-47a3-a7a0-bdf1e330477e)

Type: (Nslookup “cherry”) and notice that it fails. (This is due to no DNS record) 

![image](https://github.com/user-attachments/assets/9f04346a-b4b3-4f26-9873-50f910f9fd05)

</p>

</p>
<br />

<p>
  
Step 3: Select the 'Windows icon' at the bottom left corner. Select 'Windows Administrative Tools' and on the drop categories, select 'DNS'. The "DNS Manager" window appears. Select the 'DC-1' file, then select the 'Foward Lookup Zones'file, then select the 'mydomain.com' file. 

![image](https://github.com/user-attachments/assets/c83062af-9dd2-4010-aa12-abd92ec7e611)

To (ping "cherry"), we need to create a DNS A-record on DC-1. Use right-click in the file screen and select ' New Host (A) or (AAA)...' 

![Screen Shot 2025-01-09 at 2 13 43 PM](https://github.com/user-attachments/assets/2876e8dc-ff27-43e9-b551-c9b29255cbd3)

Under 'Name', type: cherry. Under 'IP Address' Type: 10.0.0.4 (DC-1’s Private IP address). Select the box 'Create associated pointer (PTR) record'. Click on 'Add Host'.

![image](https://github.com/user-attachments/assets/67c7e507-cf2c-4812-b611-dda2f4de4978)

Observe the 'cherry' record has been added.
![image](https://github.com/user-attachments/assets/c1e9f91e-ef0c-4784-b8d4-f2fa2d9bbc6f)


</p>
<p>

<br />

<p>
Step 4: Go back to Client-1 and try to (ping cherry). Observe that it works.
</p>
  
![ping works](https://github.com/user-attachments/assets/bf351fa5-3948-4ae4-97b0-0dd9e083c22a)

</p>

<br />

***Local DNS Cache Exercise***

<p>
Step 5: Login to Client-1 VM. Attempt to ping DC-1’s (10.0.0.4) private IP address.
</p>

![image](https://github.com/user-attachments/assets/816c2a39-2e71-4118-996f-3071a3145d92)
  
</p>

<br />

<p>
  
![image](https://github.com/user-attachments/assets/04e1f490-a230-4d23-9fb3-d300200e90ae)
</p>
<p>
Step 6: From Client-1, open PowerShell and run ipconfig /all. The output for the DNS settings should show DC-1’s private IP Address.
</p>
<br />
