  
![image](https://github.com/user-attachments/assets/fe178beb-2e4c-436d-b4d4-9c5991f3bbf6)
  
</p>

<h1> Microsoft (Azure) Cloud Virtual Machine Services</h1>
This tutorial outlines the implementation of creating a virtual machine with a Windows OS within Azure Virtual Machines. Also, successfully implementing a remote desktop login.
<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
  
<h2>Operating Systems Used </h2>

- Windows 10 (22H2)

<h2>High-Level Deployment and Configuration Steps</h2>

***Pre-req: Log on to your free trial or Pay-per-use subscription account in [Azure Portal](http://portal.azure.com)***
- Step 1: Create a Resource Group and label it 'Windows-VM'
- Step 2: Create a Virtual Machine and Configure Settings
- Step 3: Remote Desktop Log in


<h2>Deployment and Configuration Steps</h2>

<p>
 Step 1: On the search box, located on top header, type in 'resource group'. Select the 'resource group' option.

![image](https://github.com/user-attachments/assets/ead61f61-16fa-44ce-a1e0-76e9ac8b245c)

      There are two option to Select 'create' a resource group. Select either option.
      
![image](https://github.com/user-attachments/assets/002650cb-2327-4403-b0c3-bf7956863e43)

      Select your subscription (free trial or Pay-per-use). 
      In the 'Resource group name', type: 'Windows-VM'. 
      In the 'Region', type region close to your demographic. 
      Select,' Review + create' blue button. Then hit 'create'.

![image](https://github.com/user-attachments/assets/fabaea67-390a-45a5-8cce-2058fef9001a)

     Notice the notification bell icon, located on the top left corner, it will show you a list of created, deleted, or update status changes made.
    
![image](https://github.com/user-attachments/assets/8eadf593-a9b1-4965-a27c-a6350967afdf)

<p>
  

<br />
  
</p>
Step 2: Back on the top search box, type: 'virtual machine' and select the 'virtual machine' option in the drop window.

![image](https://github.com/user-attachments/assets/86a360d7-1ffd-4d19-ab41-74ba206f2777)

       Select either the top left or bottom blue box option to 'create'. Select, 'Azure Virtual Machine' option.
       
![image](https://github.com/user-attachments/assets/f16a3424-415d-402d-b526-6dabd049e2a9)


      Select your subscription (free or pay-per-use). 
      For 'Resource group', select 'Window-VM' (created in step 1).
      For 'Virtual machine name', type: 'mycomputerlab'. (Make sure the 'region' location is the same demographic selected in step 1)
      
![image](https://github.com/user-attachments/assets/05779c9f-7ffb-4a01-9fbc-52c163192007)


  ***Leave the following categories as default: availability options, zone options, availability zones, security type.***

     For 'Image' please select the 'Windows Pro 10 Version 22H2, - x64 Gen2'

![image](https://github.com/user-attachments/assets/c01f3942-4602-4668-8d2c-46bf687c5c52)

     For 'Size' please select the 'Standard_E2s_V3 -2vcpus, 16 Gig memory'
    
![image](https://github.com/user-attachments/assets/c4d22b86-07b4-4c9a-b2c6-c75564913f73)

     Create your own credentials. (make sure to follow azure's password rule)

![image](https://github.com/user-attachments/assets/8e173b0d-ac4d-45c7-a850-b2ec51dff9a9)


     Leave following categories as defaults: Public inbound ports and Select inbound ports.

     Check-off the licensing box to confirm rights.

![image](https://github.com/user-attachments/assets/c54ee64a-bd33-49d9-bc74-887b181b3bef)
    
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

