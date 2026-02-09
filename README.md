<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>Preparing AD Infrastructure in Azure</h1>
This tutorial will detail the creation of two virtual machines. One of the VMs will run Windows Server, and the other will run Windows 11. A domain will be created on the Windows Server VM, which the Windows 11 VM will subsequently join. This will enable the Windows 11 VM to become aware of other user accounts in the domain and thus demonstrate Active Directory. Active Directory is Microsoft software designed to manage user accounts and their associated properties, such as passwords and permissions, at scale. <br />


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
You will create a Resource Group that will provide the resources for the two VMs that will be created. Next, you will create a Virtual Network that will allow the VMs to communicate with each other, the Internet, and other networks. Now, you are ready to create the two VMs. The first VM (dc-1) will be the Domain Controller and will run Windows Server 2022 Datacenter, designed to provide services to other computers that may join its domain. After creating the Domain Controller VM, set its Network Interface Card Private IP Address to Static so that it won't change. This is because the second VM will be linked to the Domain Controller, and a change in the private IP Address will disrupt the connection. Lastly, you will log into dc-1 via Remote Desktop using its public IP Address. Once signed on, you will disable the Windows Defender Firewall so that connections between the two virtual machines won't be disrupted.  
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
<p>
<img src="https://imgur.com/e1l6zZy.png" alt="NIC"/>
</p>
<p>
<img src="https://imgur.com/qfYuWQC.png" alt="Static"/>
</p>
<p>
<img src="https://imgur.com/zVKKdW4.png" alt="Remote Desktop"/>
</p>
<p>
<img src="https://imgur.com/knqZZ9a.png" alt="Firewall"/>
</p>
<br />

<p>
The second VM (client-1) will run on Windows 11 Pro, which is designed for a single user. This VM will join the Domain Controller. After creating this VM, set its DNS settings to DC-1's Private IP Address. So, whenever Client-1 tries to find either a name or an IP address, it will do so through the Domain Controller. Using Remote Desktop, log into Client-1 using its Public IP Address. Open Windows PowerShell. Send a Ping to DC-1's Private IP Address to test the connectivity between the two VMs. Run ipconfig /all to provide a snapshot of client-1's network configuration. One thing you will see is DC-1's Private IP Address listed with the DNS Servers. 
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
