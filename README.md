  
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

     Check-off the licensing box to confirm rights. Select 'Review + Create' button and then 'Create'.

![image](https://github.com/user-attachments/assets/6ff21c14-c728-4104-b050-5e5c72f73c72)
    
</p>

</p>
<br />

<p>
  
Step 3: After you noticed that the 'mycomputerlab' VM was deployed. Return to the Virtual machines category via the search box. You should be able to view a snapshot of your VM details:

![image](https://github.com/user-attachments/assets/82713fe0-556f-4366-ad1a-ebf4f49f791e)

       Highlight and copy the 'Public IP Address' designated for 'mycomputerlab' VM. Open the Windows App (if using a Mac OS). 
       On the top left courner, select the plus (+) icon. Select 'Add PC'. 
       Paste the 'Plublic IP Address' for 'mycomputerlab' for the PC Name.
       Type 'mycomputerlab' for Friendly Name. Select 'Add'.
       
![image](https://github.com/user-attachments/assets/87136e90-98d4-49fa-a15e-cd25ab069997)

      Double-click on the new 'mycomputerlab' PC. Enter Credential you created for this VM. Select 'Continue'.
      
![image](https://github.com/user-attachments/assets/045afd26-8ced-4726-bf96-5612aff87b67)

      You have successfully logged into your Virtual machine and are now operating in Windows OS. 
      
![image](https://github.com/user-attachments/assets/9aadf262-069f-471e-8763-c1c445f1e9dc)

![image](https://github.com/user-attachments/assets/01b85415-8fb2-4b86-a9a8-9876d98ad71c)


</p>
<p>

<br />

