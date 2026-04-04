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
 
</p>
<p>
<img src="https://imgur.com/FBfC9Nm.png" alt="Client-1"/>
</p>
<p>
<img src="https://imgur.com/Vb9t1oZ.png" alt="Windows 11 Pro"/>
</p>
<p>
<img src="https://imgur.com/fs0L21M.png" alt="Eligible License"/>
</p>
<p>
<img src="https://imgur.com/OWuc5xX.png" alt="Network Interface"/>
</p>
<p>
<img src="https://imgur.com/yPuOzlo.png" alt="Client-1 NIC"/>
</p>
<p>
<img src="https://imgur.com/AFmoWFT.png" alt="DNS Server"/>
</p>
<p>
<img src="https://imgur.com/M00YDWk.png" alt="Ping"/>
</p>
<p>
<img src="https://imgur.com/M9MGT12.png" alt="ipconfig"/>
</p>
