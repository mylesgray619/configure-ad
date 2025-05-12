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

- Install Active Directory
- Create a Domain Admin user with the domain
- Join Client-1 to the domain
- Setup Remote Desktop for non-administrative users on Client-1
- Create a bunch of additional users and attempt to log into client-1 with one of the users 

<h2>Deployment and Configuration Steps</h2>

<p>
<img src="https://i.imgur.com/1QB6F3W.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Here im installing Active directory domain servies from the server manager as part of the primary domain contoller for "client-1" (the other computer).
</p>
<br />

<p>
<img src="https://i.imgur.com/qcA1bXx.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Here is the second part of the process in which I have to add new forest as mydoamin.com to prmote the active directory as Domain controller. After installing, the computer will restart then I would log back in as mydomain.com\username.
</p>
<br />

<p>
<img src="https://i.imgur.com/PkHCS6H.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Here I go to Active Directory Users and Computers to create two organizational units one for employees and the other for admin. This will organize user access.
</p>
<br />

<p>
<img src="https://i.imgur.com/iaqJwuE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Here I create a new employee named Jane that is added to Domain Admins security group. This will make her the head admin in the computer. Afterwards I would log off then sign back in as her domain username.
</p>
<br />

<p>
<img src="https://i.imgur.com/MoNcVHZ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Here I im logging back in as "client-1" on the other computer. I then click on systems, click on rename this pc (advance), then lastly add client-1 to the domain under mydomain.com. The computer will restart afterwards.
</p>
<br /> 

<p>
<img src="https://i.imgur.com/u8NsEIT.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Here I logged into the Domain Controller to verify that "Client-1" has shown up into the active directory users and computers.
</p>
<br /> 

<p>
<img src="https://i.imgur.com/1NNWVd1.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Here, I then created an additional organizational unit (_CLIENTS) then dragged client-1 into the unit.
</p>
<br /> 

<p>
<img src="https://i.imgur.com/I0tuHHp.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Here Im logged into client-1. I open the system properties, then click on remote desktop this allows me to add domain users to have access to the remote desktop. By doing this I can now log into client-1 as a normal non-administrative user.
</p>
<br /> 

<p>
<img src="https://i.imgur.com/wUsoc3v.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Here im logged into the domain controller. I opened powershell and runned it as a administrator. Then I created a new file and pasted contents of a script into it. By doing this im able to run the script and observe user accounts being created.
</p>
<br /> 

<p>
<img src="https://i.imgur.com/XeEqsqJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
After the script has created the accounts, I can go to the ADUC and observe the accounts that was create in the organiztional unit _EMPLOYEES.
</p>
<br /> 

<p>
<img src="https://i.imgur.com/ByI5Gt6.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Here I was able to successfully log into Client-1 with one of the user accounts that was created. 
</p>
<br /> 
