<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Preparing AD Infrastructure in Azure</h1>
This tutorial will detail the creation of two virtual machines. One of the VMs will run Windows Server, and the other will run Windows 11. A domain will be created on the Windows Server VM, which the Windows 11 VM will subsequently join. This will enable the Windows 11 VM to become aware of other user accounts in the domain and thus demonstrate Active Directory. Active Directory is Microsoft software designed to manage user accounts and their associated properties, such as passwords and permissions, at scale. <br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure 
- Remote Desktop
- Windows Defender Firewall
- Microsoft PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022 Datacenter (Domain Controller)
- Windows 11 Pro (25H2) (Client)

<h2> Configuration Steps</h2>

<p>
Create a Resource Group (Active-Directory-Lab) that will provide resources for the two VMs.  
</p>
<p>
<img src="https://imgur.com/u5PNsGp.png" alt="Resource Group"/>
</p>
<p>
Create a Virtual Network (Active-Directory-VNet) that will allow the two VMs to communicate with each other. List Active-Directory-Lab as the Resource Group. 
</p>
<p>
<img src="https://imgur.com/6W5WVPZ.png" alt="Virtual Network"/>
</p>
<br />

<p>
Create a VM that will serve as the Domain Controller (dc-1). Use the Resource Group from earlier (Active-Directory-Lab). 
</p>
<p>
<img src="https://imgur.com/yad7ztr.png" alt="VM 1"/>
</p>
<p>
Use the same Region (South Central US) that you used for the RG and VNet. 
</p>
<p>
<img src="https://imgur.com/PybeReG.png" alt="dc-1"/>
</p>
<p>
This VM will run Windows Server 2022 Datacenter, which is designed to provide services to other computers that will join its domain. The size must be one that has 2 vcpus and 8 Gib memory (Standard_D2s_v3 - 2 vcpus, 8 Gib memory).
</p>
<p>
<img src="https://imgur.com/1CqYtPB.png" alt="Windows Server 2022 Datacenter"/>
</p>
<p>
Enter a Username and Password that will be used for Remote Desktop access.
</p>
<p>
<img src="https://imgur.com/Qngjoht.png" alt="labuser"/>
</p>
<p>
Check the two boxes that concern a Windows Server License. 
</p>
<p>
<img src="https://imgur.com/GWjkHM3.png" alt="Windows Server License"/>
</p>
<p>
In the Networking section, select Active-Directory-VNet as the Virtual Network. 
</p>
<p>
<img src="https://imgur.com/P7s6oAg.png" alt="Networking"/>
</p>
<br />

<p>
