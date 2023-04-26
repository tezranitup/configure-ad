<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />


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

- Step 1: Install Active Directory
- Step 2: Create an Admin and Normal User Account in AD
- Step 3: Join Client-1 to your domain (mydomain.com)
- Step 4: Setup Remote Desktop for non-administrative users on Client-1

<h2>Deployment and Configuration Steps</h2>

<p>
<img src="https://i.imgur.com/4HTgqbR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
The first step is to join the domain controller click on add roles and features in server manager and keep clicking next and intall after that click on the orange triangle in the top right then click prote to domain controller then keep clicking next then setup a new forest and give it a domain name (tezdomain.com) then install it then log back into it with domain name first then \username.
</p>
<br />

<p>
<img src="https://i.imgur.com/qMPom1C.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
After you've download the AD on server manager go to tools or go to start and type Active Directory Users and Computers after that click on the folder that has you domain name then right click it and create a new organizational folder called employees and one called admins. When you finish with that click on admins folder  and right click in the blank area to the right and create a new user then right click the user you just made and go to properties then go to the tab member of then click then add a new one called domain admins by click add and type domain then check names and apply it. After that is done logoff of of the domain controller then log back in with the new user you created the same way in step one but with the user you made in Active Directory Users and Computers.
</p>
<br />

<p>
<img src="https://i.imgur.com/xaimOFi.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
after you've logged back in go to the aure portal and copy the domain control public IP then go to the other virtual machine and go to network then go to the network interfase to the right then go to the DNS server and make a custom DNS thats the same as the public IP of the domain controller then from the azure portal restart Client-1(the other domain) then log back in using the orgiginal username from the very beginning then right click the start then go to systems then rename this PC(advanced) then change and click on domain and put in the domain name that that you created then login with the domain acount you use to login with the domain controller.
</p>
<br />

<p>
<img src="https://i.imgur.com/iu0soEj.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
after you've logged back in to client-1 go way to the systems from the last step but this time go to remote desktop and add domain users then press ok then put the information you just used to login to client-1.
</p>
<br />
