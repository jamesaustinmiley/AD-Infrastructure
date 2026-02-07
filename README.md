<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Preparing AD Infrastructure in Azure (Azure)</h1>
This tutorial will detail the creation of two virtual machines. One of the VMs will be running Windows server and the other will be running Windows 11. A domain will be created on the Windows Server VM, which the Windows 11 VM will subsequently join. This will enable the Windows 11 VM to become aware of the other user accounts that are part of the domain and will thus demonstrate Active Directory. Active Directory is Microsoft software that is designed for the management of user accounts and their associated properties, such as passwords and permissions, on a large, centralized scale.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure 
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022 Datacenter (Domain Controller)
- Windows 11 Pro (25H2) (Client)

<h2>Deployment and Configuration Steps</h2>

<p>
You will create a Resource Group that will provide the resources for the two VMs that will be created. Next, you will create a Virtual Network that will allow the VMs to communicate with each other, the Internet, and other networks. Now, you are ready to create the two VMs. The first VM (dc-1) will be the Domain Controller and will run on Windows Server 2022 Datacenter, which is designed to provide services to other computers that may join its domain. 
</p>
<p>
<img src="https://imgur.com/TWUaXK1.png" alt="Resource Group"/>
</p>
<p>
<img src="https://imgur.com/UdtWa6Y.png" alt="Virtual Network"/>
</p>
<p>
<img src="https://imgur.com/ckBOmqA.png" alt="dc-1"/>
</p>
<p>
<img src="https://imgur.com/KC1DAuR.png" alt="Windows Server"/>
</p>
<p>
<img src="https://imgur.com/SIfzTti.png" alt="Windows Server License"/>
</p>
<p>
<img src="https://imgur.com/lzLbsIy.png" alt="Networking"/>
</p>
<br />

<p>

<p>
The second VM will run on Windows 11 Pro, which is designed for a single user. This VM will join the Domain Controller. 
