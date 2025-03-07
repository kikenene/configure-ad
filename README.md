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
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Create Resource group
- Create Virtual Network
- Create Virtual Machines
- Disable Firewall
- Change NIC private IP from Dynamic to Static
- Ping a Virtual Machine from a Virtual Machine server

<h2>Deployment and Configuration Steps</h2>

<p>
  
![step 1 create resource group](https://github.com/user-attachments/assets/fe1b49fa-955d-461c-a7c9-5b53dee7541a)

</p>
<p>
Had to create a Resource Group named "Active-Directory-Lab" to put the other elements in.
</p>
<br />

<p>

![step 2 created virtual network](https://github.com/user-attachments/assets/3fd04bdc-5f24-4dc7-84af-d5a4dbf77a6d)

</p>
<p>
Next, I created a Virtual Network by the name of "Active-Directory-Vnet."
</p>
<br />

<p>
  
![step 3 created virtual machine 1](https://github.com/user-attachments/assets/ab0dbfa3-f1c6-4e30-a87a-e9d8d9d6ef2f)

![step 3 created virtual machine 2](https://github.com/user-attachments/assets/20afab9d-4270-4437-8b32-29f527d45943)

</p>
<p>
Create a Virtual Machine for the Domain Controller named "dc-1." The image was set to Windows Server 2022.
</p>
<br />

<p>
  
![step 4 change from dynamic to static](https://github.com/user-attachments/assets/5d8e06d0-d05b-4570-b5a2-f5515dc5f359)

</p>
<p>
Changed the DC-1 NIC private IP from Dynamic to Static.
</p>
<br />

<p>
  
![step 5 turned off firewall in vm dc-1](https://github.com/user-attachments/assets/b98dc716-b6c9-4fe2-bea1-7fad8f594164)

</p>
<p>
Opened the DC-1 Virtual Machine with Remote Desktop. Then, opened the wf.msc to deactivate the firewalls.
</p>
<br />

<p>
  
![step 6 create client 1 vm](https://github.com/user-attachments/assets/abe01585-afb8-4c01-8987-aafa91f05c94)

![step 6 create client 1 vm 2](https://github.com/user-attachments/assets/6a9c38c1-d8be-4e03-86b6-32551e818578)

![step 6 both vms](https://github.com/user-attachments/assets/3812537b-e607-4805-9669-8c514c67fa90)

</p>
<p>
Create the Virtual for Client 1 named "client-1." The image was set to Windows 10.
</p>
<br />

<p>
  
![step 7 set client1 DNS setting to DC1 private IP](https://github.com/user-attachments/assets/f5399956-1c82-47b8-a4c9-c70ebdd71965)

</p>
<p>
Accessed the Client 1 DNS settings and set it to DC-1's private IP address.
</p>
<br />

<p>
  
![step 8 ping dc1 on client1 powershell](https://github.com/user-attachments/assets/d92955bd-5c3a-4549-8d05-dd5eafc67cb1)

![step 8 ping dc1 on client1 powershell active](https://github.com/user-attachments/assets/d740549d-3399-4b46-af1b-93e7ac420223)

</p>
<p>
Opened Client 1's VM from Remote Desktop. Accessed DC-1 VM to open Powershell and pinged Client 1. It showed that the ping was a success.
</p>
<br />

<p>
  
![step 9 ipconfig all on client1](https://github.com/user-attachments/assets/bff9e519-a3ea-4a43-b139-ab551f0ac50b)

![step 9 ipconfig all on client1 active](https://github.com/user-attachments/assets/70e74002-afaf-4285-b42a-63afe71c3751)

</p>
<p>
I opened Powershell in Client 1 VM and typed "ipconfig /all" to showcase all of the DNS cache within it. Now the Active Directory is fully configured.
</p>
<br />
