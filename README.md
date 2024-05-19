<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Network File Shares & Permissions</h1>
Continuing from the Active Directory Lab, this tutorial explains how to share files and folders over a network and grant read and write permissions to specific groups and users. <br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure
- 2 Virtual Machines (DC-1/Client-1)
- 2 Remote Desktop Instances
- Active Directory Domain Services
- PowerShell (Used to help distinguish between Virtual Machines)

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>Steps & Procedures</h2>

- Creating Sample File Shares & Granting Permissions on DC-1
- Navigating to Active Directory Users and Computers
- Attempting to access File Shares 

<h2>Creating Sample File Shares & Granting Permissions on DC-1</h2>

![image](https://github.com/HectorRivera-Perea/network-file-shares-permissions/assets/142694152/9ac7318e-2bf9-4061-be77-ac95b3390fd3)

Retrieve the Public IP Address:

- Access the Azure portal.
- Navigate to your Virtual Machine's details.
- Find and copy the Public IP Address of your Domain Controller.

</p>
<br />

<p>

![image](https://github.com/HectorRivera-Perea/network-file-shares-permissions/assets/142694152/0d2f8080-1a8b-4e88-8e90-56f17ce8ad46)

</p>
<p>
Remote Desktop Connection:

- Open Remote Desktop Connection on your computer.
- Enter the copied Public IP Address.
- Log in using your Domains Admin account credentials.
</p>
<br />

<p>

  ![image](https://github.com/HectorRivera-Perea/network-file-shares-permissions/assets/142694152/4e5a2f4f-c088-407d-848c-cc9db7737faa)

</p>
<p>
  
Open File Explorer:

- Click the folder icon on the taskbar or press Win + E.

Find the <b>"C: Drive"</b>:
- Click <b>"This PC"</b> and then double-click on <b>"C: Drive."</b>

Create Folders:

Right-click inside the C: Drive window, select <b>"New,"</b> then <b>"Folder."</b>
Create the following folders:
- read-access
- write-access
- no-access
- accounting
  
</p>
<br />

![image](https://github.com/HectorRivera-Perea/network-file-shares-permissions/assets/142694152/e05b01df-5555-4dbd-9018-011f3cb2d8c7)

Open Folder Properties:

- Right-click on one of the newly created folders (e.g., read-access).
- Click on <b>"Properties."</b>
- Access Sharing Settings:

In the Properties window, go to the "Sharing" tab.
- Click on <b>"Share..."</b>

Add Users and Set Permissions:
- In the <b>"Network Access"</b> window, type Domain Users and click <b>"Add."</b>
- Set the desired permission level (Read, Write, etc.) for Domain Users.
- Click <b>"Share"</b> and then <b>"Done."</b>

<h2>Navigating to Active Directory Users and Computers</h2>

Open Active Directory Users and Computers:
- Use the search bar on your Domain Controller to find and open <b>"Active Directory Users and Computers."</b>

Find Users in _EMPLOYEES Folder:
- Expand your domain (e.g., mydomain.com).
- Open the<b>_EMPLOYEES</b> folder.
- Select a user to log into the Client-1 Virtual Machine.

![image](https://github.com/HectorRivera-Perea/network-file-shares-permissions/assets/142694152/b4f5a402-a06f-4572-ae64-00bea93d931a)

<h2>Attempting to access File Shares</h2>

Go back into your Azure portal - Virtual Machines options:
- Retrieve your Client-1 IP address and open a second instance of Remote Desktop Connection.

![image](https://github.com/HectorRivera-Perea/network-file-shares-permissions/assets/142694152/7e7ff52b-f138-4e1f-aa2a-a4ef2e88148d)

<b>*Pro Tip - If at anytime during this process, you get confused between the two different Virtual Machines, use the "Command Prompt" window and use the following commands to help you better identify which one is in use:*
- Command - *hostname*
- Command - *whoami* </b>

![image](https://github.com/HectorRivera-Perea/network-file-shares-permissions/assets/142694152/1484add7-de24-41d6-a787-f6b312079f97)

Access Shared Folders:
- Open <b>"File Explorer."</b>
- Type <b>\\DC-1</b> into the search bar to access the shared folders.

![image](https://github.com/HectorRivera-Perea/network-file-shares-permissions/assets/142694152/10de2d5b-88ab-49c0-87f8-05e83527e425)

Review Folder Permissions:
- Open each folder.
- Take notes on the permissions granted.
- Observe the differences between what Users can access and what Admins can access.

<h2>Conclusion</h2>
You now have the knowledge and understanding of how file sharing works and how to implement it in your future networking projects.










