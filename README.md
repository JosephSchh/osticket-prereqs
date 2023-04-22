# osticket-prereqs
<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Microsoft Azure Virtual Machine
- OsTicket [Installation Files](https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6)
- [Heidi SQL](https://docs.google.com/document/d/1WovrX2DaS9xkfaSr4LXyB4YnnWpXIgPCMMbbfgHmGVw/edit)

<h2>Installation Steps</h2>
<p>
<img src="https://i.imgur.com/Xuzq390.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Part 1 (Create Virtual Machine in Azure):
To create a Windows 10 Virtual Machine in Azure, start by creating a Resource Group. Once you have created the Resource Group, create a Windows 10 Virtual Machine with 2-4 Virtual CPUs. Then click review and create.
</p>
<br />

<p>
<img src="https://imgur.com/Rds90BJ.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
Once you have created the Windows Virtual Machince, connect to its Public IP Address by using Remote Desktop.
</p>
<br />

<p>
<img src="https://imgur.com/jejunOC.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Now that you have connected to the VM, navigate to control panel -> uninstall or change a program -> Turn Windows features on or off. Then enable the following: Internet Information Services -> World Wide Web Services -> Application Developement Features -> CGI.
</p>
<br />

<p>
<img src="https://imgur.com/2YzadVK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next, click on the link to the osTicket Installation Files which is located in List of Prerequisites section. You are not going to be download these on your own computer but inside the Virtual Machine so copy the link for the Installation Files and paste it into your Virtual Machines web browser. Then download and install  PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi) aswell as Rewrite Module (rewrite_amd64_en-US.msi). Then, create the directory C:\PHP
</p>
<br />

<p>
<img src="https://imgur.com/j7AbNlq.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next up, download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and unzip the contents into C:\PHP
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
---
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Continue setting up osTicket in the browser by entering "osTicket" for the MySQL Database, "root" for the MySQL Username, and "Password1" for the MySQL Password. Click "Install Now!". Once installed, browse to your help desk login page at http://localhost/osTicket/scp/login.php. Your end users' osTicket URL is http://localhost/osTicket/.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
To clean up, delete C:\inetpub\wwwroot\osTicket\setup and set permissions to "Read" only for C:\inetpub\wwwroot\osTicket\include\ost-config.php.
</p>
<br />
