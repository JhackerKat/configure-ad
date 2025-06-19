<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of Active Directory within Azure Virtual Machines.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How to Deploy on-premises Active Directory within Azure Compute](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Step 1: Preparing AD Infrastructure in Azure
- Step 2: Deploying Active Directory
- Step 3: Creating Users With Powershell
- Step 4: Group Policy And Managing Accounts

<h2>Deployment and Configuration Steps</h2>

<p>
<img width="466" alt="Step 1  (a" src="https://github.com/user-attachments/assets/85d8a8c3-61f2-44ee-a7ae-3b8b1881a8f9" />
</p>
<p>
Step 1. Create a Resource Group
</p>
<br />

<p>
<img width="462" alt="Step 1  (b" src="https://github.com/user-attachments/assets/f104a238-6137-4529-859e-1a67a74b6030" />
</p>
<p>
Step 2. Create a Virtual Network
</p>
<br />

<p>
<img width="466" alt="Step 1  (c" src="https://github.com/user-attachments/assets/2b680567-61f0-43d6-8350-74c4f2368d8d" />
</p>
<p>
Step 3. Create the Domain Controller VM (Windows Server 2022) named "DC-1"
</p>
<br />

<p>
<img width="466" alt="Step 1  (d" src="https://github.com/user-attachments/assets/c60666a5-85ab-4e7a-8d41-61c911b2e9c4" />
</p>
<p>
Step 4. Create the Client VM (Windows 10) named "Client-1"   
</p>
<br />

<p>
<img width="465" alt="Step 1  (e" src="https://github.com/user-attachments/assets/c8e5eb5d-c9f7-4b05-a771-8e8bc305e6bc" />
</p>
<p>
Step 5. Set Domain Controller's NIC Private IP address to be static
</p>
<br />

<p>
<img width="501" alt="Step 1  (f" src="https://github.com/user-attachments/assets/8c66ded5-467b-445f-ba22-76713f4322f7" />
</p>
<p>
Step 6. Log into the VM and disable the Windows Firewall
</p>
<br />

<p>
<img width="466" alt="Step 1  (g" src="https://github.com/user-attachments/assets/699c7f00-8bf9-4cd4-a00f-50efe617ebaf" />
</p>
<p>
Step 7. Set Client-1's DNS settings to DC-1's Private IP address and then log in
</p>
<br />

<p>
<img width="501" alt="Step 1  (h" src="https://github.com/user-attachments/assets/74fd14b3-3a60-4777-9e88-08b9e3ca7803" />
</p>
<p>
Step 8. Attempt to ping DC-1's private IP address
• Ensure the ping succeeded
</p>
<br />

<p>
<img width="498" alt="Step 1  (i" src="https://github.com/user-attachments/assets/f1559e4d-79f1-4561-84cc-63a230b4d991" />
</p>
<p>
Step 9. From Client-1, open PowerShell 
and run ipconfig /all
• The output for the DNS settings should show
 DC-1's private IP Address
</p>
<br />
