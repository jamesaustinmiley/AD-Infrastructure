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
