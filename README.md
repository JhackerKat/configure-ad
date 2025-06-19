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
Step 1. (a) Create a Resource Group
</p>
<br />

<p>
<img width="462" alt="Step 1  (b" src="https://github.com/user-attachments/assets/f104a238-6137-4529-859e-1a67a74b6030" />
</p>
<p>
Step 1. (b) Create a Virtual Network
</p>
<br />

<p>
<img width="466" alt="Step 1  (c" src="https://github.com/user-attachments/assets/2b680567-61f0-43d6-8350-74c4f2368d8d" />
</p>
<p>
Step 1. (c) Create the Domain Controller VM (Windows Server 2022) named "DC-1"
</p>
<br />

<p>
<img width="466" alt="Step 1  (d" src="https://github.com/user-attachments/assets/c60666a5-85ab-4e7a-8d41-61c911b2e9c4" />
</p>
<p>
Step 1. (d) Create the Client VM (Windows 10) named "Client-1"   
</p>
<br />

<p>
<img width="465" alt="Step 1  (e" src="https://github.com/user-attachments/assets/c8e5eb5d-c9f7-4b05-a771-8e8bc305e6bc" />
</p>
<p>
Step 1. (e) Set Domain Controller's NIC Private IP address to be static
</p>
<br />

<p>
<img width="501" alt="Step 1  (f" src="https://github.com/user-attachments/assets/8c66ded5-467b-445f-ba22-76713f4322f7" />
</p>
<p>
Step 1. (f) Log into the VM and disable the Windows Firewall
</p>
<br />

<p>
<img width="466" alt="Step 1  (g" src="https://github.com/user-attachments/assets/699c7f00-8bf9-4cd4-a00f-50efe617ebaf" />
</p>
<p>
Step 1. (g) Set Client-1's DNS settings to DC-1's Private IP address and then log in
</p>
<br />

<p>
<img width="501" alt="Step 1  (h" src="https://github.com/user-attachments/assets/74fd14b3-3a60-4777-9e88-08b9e3ca7803" />
</p>
<p>
Step 1. (h) Attempt to ping DC-1's private IP address
• Ensure the ping succeeded
</p>
<br />

<p>
<img width="498" alt="Step 1  (i" src="https://github.com/user-attachments/assets/f1559e4d-79f1-4561-84cc-63a230b4d991" />
</p>
<p>
Step 1. (i) From Client-1, open PowerShell 
and run ipconfig /all
• The output for the DNS settings should show
 DC-1's private IP Address
</p>
<br />

<p>
<img width="500" alt="Step 2  (a" src="https://github.com/user-attachments/assets/86007a15-fe2b-4525-be47-5382d7af56f7" />
</p>
<p>
Step 2. (a) Login to DC-1 and install Active Directory Domain Services    
</p>
<br />

<p>
<img width="499" alt="Step 2  (b" src="https://github.com/user-attachments/assets/cfd2b520-bc86-4637-8361-51c9838d8e14" />
</p>
<p>
Step 2. (b) Setup a new forest as mydomain.com
</p>
<br />

<p>
<img width="497" alt="Step 2  (c" src="https://github.com/user-attachments/assets/747d06e4-bfbf-4c6a-aa63-b24311943eb0" />
</p>
<p>
Step 2. (c) Log back into DC-1 as user: mydomain.com labuser
</p>
<br />

<p>
<img width="500" alt="Step 2  (d" src="https://github.com/user-attachments/assets/dfd0d5e2-82cb-412b-beed-b5e88bceceba" />
</p>
<p>
Step 2. (d) Create an organizational unit called "_EMPLOYEES"
</p>
<br />

<p>
<img width="500" alt="Step 2  (e" src="https://github.com/user-attachments/assets/eaa0deb6-68bf-4a18-b3e8-994d15ba7a91" />
</p>
<p>
Step 2. (e) Create an organizational unit called "_ADMINS"
</p>
<br />

<p>
<img width="501" alt="Step 2  (f" src="https://github.com/user-attachments/assets/11356d9e-0bdf-4ba7-a328-aeba38865f87" />
</p>
<p>
Step 2. (f)  Create a new employee named 
"Jane Doe" (same password) with the username of
"jane_admin"  
</p>
<br />

<p>
<img width="500" alt="Step 2  (g" src="https://github.com/user-attachments/assets/c3b81992-c931-40b1-a3a3-d0444007e8ac" />
</p>
<p>
Step 2. (g) Add jane_admin to the "Domain Admins" Security Group
</p>
<br />

<p>
<img width="500" alt="Step 2  (h" src="https://github.com/user-attachments/assets/b444a18c-bc36-4e26-8f56-f00f18de5ed1" />
</p>
<p>
Step 2. (h)  Log out / close the connection to DC-1 and log back in as "mydomain.com/jane_admin"
</p>
<br />

<p>
<img width="499" alt="Step 2  (i" src="https://github.com/user-attachments/assets/da7789cb-46a1-4221-ac02-a0d408659f25" />
</p>
<p>
Step 2. (i) Login to Client-1 as the original local admin (labuser) and join it to the domain (computer will restart)
</p>
<br />

<p>
<img width="500" alt="Step 2  (j" src="https://github.com/user-attachments/assets/fad456af-8209-447e-9d65-a9ed40d22e73" />
</p>
<p>
Step 2. (j) Login to Client-1 as the original local admin (labuser) and join it to the domain (computer will restart)
</p>
<br />

<p>
<img width="499" alt="Step 2  (k" src="https://github.com/user-attachments/assets/535b41bb-c604-4b75-81b3-f5d3a6a03244" />
</p>
<p>
Step 2. (k) Login to the Domain Controller and verify Client-1 shows up in ADUC
Create a new OU named "_CLIENTS" and drag Client-1 into there
</p>
<br />

<p>
<img width="501" alt="Step 2  (l" src="https://github.com/user-attachments/assets/bb9cb104-6554-4799-9701-57feb24d6ef5" />
</p>
<p>
Step 2. (l) Log into Client-1 as mydomain.com\jane_admin
</p>
<br />

<p>
<img width="501" alt="Step 2  (m" src="https://github.com/user-attachments/assets/fc70f4bb-627d-4fc2-ace0-00a8b4fd525a" />
</p>
<p>
Step 2. (m) Step 12. Open system properties Click "Remote Desktop" Allow "domain users" access to remote desktop 
</p>
<br />

<p>
<img width="502" alt="Step 2  (n" src="https://github.com/user-attachments/assets/0210e918-2ba0-4593-a590-c51963c7672c" />
</p>
<p>
Step 2. (n) Login to DC-1 as jane_admin
Open PowerShell _ise as an administrator
Create a new File and paste the contents of the script into it
</p>
<br />

<p>
<img width="500" alt="Step 2  (o" src="https://github.com/user-attachments/assets/d15f8b73-6f96-40d2-aca5-6534b93c2e9b" />
</p>
<p>
Step 2. (o) When finished, open ADUC and observe the accounts in the appropriate OU "_EMPLOYEES" attempt to log into Client-1 with one of the accounts (take note of the password in the script)
</p>
<br />

