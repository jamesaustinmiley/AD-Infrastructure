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

<h2>Steps</h2>

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
Access the Network Settings of the dc-1 VM and click on Network Interface / IP Configuration Card. 
</p>
<p>
<img src="https://imgur.com/ZXie15E.png" alt="dc-1 Network Settings"/>
</p>
<p>
Click on ipconfig1 and set the Private IP address settings to Static so that it won't change and interfere with connection between the two VMs. 
</p>
<p>
<img src="https://imgur.com/vACl9RN.png" alt="ipconfig1"/>
</p>
<p>
<img src="https://imgur.com/4ggw9hh.png" alt="Static"/>
</p>
<br />

<p>
Connect to dc-1, via Remote Desktop, using the VM's Public IP Address and login credentials. 
</p>
<p>
<img src="https://imgur.com/AYtiYqc.png" alt="Remote Desktop dc-1"/>
</p>
<p>
Right-click the Windows icon and select Run. Type wf.msc to access the Windows Defender Firewall. 
</p>
<p>
<img src="https://imgur.com/fcNkfil.png" alt="wf.msc"/>
</p>
<p>
Click Windows Defender Firewall Properties  
</p>
<p>
<img src="https://imgur.com/TjmDt79.png" alt="Windows Defender Firewall 1"/>
</p>
<p>
Change the Firewall State to Off in the Domain, Private, and Public Profile tabs. Click Apply and OK at the bottom of each screen. This will allow for a clear connection between the two VMs without firewall interference.
</p>
<p>
<img src="https://imgur.com/LoZ7JNm.png" alt="Domain"/>
</p>
<p>
<img src="https://imgur.com/lqiW3YR.png" alt="Private"/>
</p>
<p>
<img src="https://imgur.com/4Dv0ona.png" alt="Public"/>
</p>
<p>
<img src="https://imgur.com/pXoKiRD.png" alt="Windows Defender Firewall 2"/>
</p>
<br />

<p>
Create a second VM (client-1) that will join the Domain Controller. This will enable the Windows 11 VM to become aware of other user accounts in the domain, thereby demonstrating Active Directory. Use Active-Directory-Lab as the Resource Group. 
</p>
<p>
<img src="https://imgur.com/g2BMZ88.png" alt="VM 2"/>
</p>
<p>
Use South Central US as the Region. 
</p>
<p>
<img src="https://imgur.com/FnsOLqS.png" alt="client-1"/>
</p>
<p>
Client-1 will run on Windows 11 Pro, version 25H2. It's size will be Standard D2s_v3 - 2 vcpus, 8 Gib Memory. 
</p>
<p>
<img src="https://imgur.com/7OB1Bc4.png" alt="Windows 11 Pro"/>
</p>
<p>
Create login credentials that will be used for Remote Desktop access. 
</p>
<p>
<img src="https://imgur.com/I8WuFy3.png" alt="login credentials"/>
</p>
<p>
Check the box concerning a Windows 11 License. 
</p>
<p>
<img src="https://imgur.com/yDpbOJb.png" alt="Windows 11 License"/>
</p>
<p>
Use Active-Directory-VNet as the Virtual Network.
</p>
<p>
<img src="https://imgur.com/letfHDv.png" alt="VN"/>
</p>
<br />

<p>
Access the Network Settings of the client-1 VM and click on the Network Interface / IP Configuration Card. 
</p>
<p>
<img src="https://imgur.com/UCUpnwc.png" alt="client-1 NIIP Card"/>
</p>
<p>
Set client-1's DNS settings to dc-1's Private IP Address by clicking on DNS Servers, selecting Custom, and entering dc-1's Private IP. Restart client-1 to enable the change. 
</p>
<p>
<img src="https://imgur.com/OCbmhMC.png" alt="DNS"/>
</p>
<p>
<img src="https://imgur.com/7DGco6u.png" alt="Restart"/>
</p>
<br />

<p>
Log in to the client-1 VM on Remote Desktop using its Public IP Address. 
</p>
<p>
<img src="https://imgur.com/7BUgBb8.png" alt="client-1 login"/>
</p>
<p>
Run Windows PowerShell as an Administrator.
</p>
<p>
<img src="https://imgur.com/IfSrf8O.png" alt="PowerShell Administrator"/>
</p>
<p>
Ping dc-1's Private IP to show that the two VMs can connect over the network. 
</p>
<p>
<img src="https://imgur.com/wj0EfEA.png" alt="Ping"/>
</p>
<p>
In PowerShell, run the ipconfig /all command to display the client-1 VMs information. Within this list, you should see the dc-1 VMs Private Ip (10.0.0.4) listed opposite DNS Servers. 
</p>
<p>
<img src="https://imgur.com/jPOlBfH.png" alt="ipconfig /all"/>
</p>
