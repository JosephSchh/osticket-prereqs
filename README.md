# osticket-prereqs
<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />



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
<img src="https://imgur.com/m77F73k.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Now, go back to installation files and install VC_redist.x86.exe and MySQL 5.5.62 (mysql-5.5.62-win32.msi). Follow these instructions when installing MySQL: Typical Setup -> Launch Configuration Wizard (after install) ->
Standard Configuration -> Root Password: Password1
</p>
<br />

<p>
<img src="https://imgur.com/zfb8wiW.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Awesome! Next click on the start menu and type IIS, right click it and run it as administrator. Double click "PHP Manager" and then click "Register new PHP version". Then navigate to directory C:\PHP and open php-cgi. When that is done, go back to the osTicket homepage where you were beforer and click restart in the top right corner.
</p>
<br />

<p>
<img src="https://imgur.com/epAhbSt.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Great! Now go to Installation Files and download and extract osTicket-v1.15.8.zip. Once that is done move the "upload" folder to c:\inetpub\wwwroot. Within c:\inetpub\wwwroot, Rename “upload” to “osTicket”, the end result should look like the image above.
</p>
<br />

<p>
<img src="https://imgur.com/pVJjx8q.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next, Open IIS, and stop and start the server or click restart. In IIS, click Sites-> Default-> osticket. On the right, click "Browse*:80"
</p>
<br />

<p>
<img src="https://imgur.com/on0XUcW.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://imgur.com/XNC9WYR.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
After clicking on "Browser:80", this site should pop up. As you can see some of the extenstions are not enabled that we need to enable. Go back to IIS, then navigate to Sites-> Default-> osTicket, then double-click "PHP Manager". Click "Enable or disable an extension". Enable: php_imap.dll, php_intl.dll, php_opcache.dll. Refresh the osTicket site in your browse, observe the changes.
</p>
<br />

<p>
<img src="https://imgur.com/Wq5oAOn.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://imgur.com/ChRrW6i.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Fantastic! Next rename From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
                         To: C:\inetpub\wwwroot\osTicket\include\ost-config.php
  After this, right-click on this file then click Properties -> Security -> Advanced -> Disable Inheritance -> Remove All Permissions -> Add Permissions -> Select a Principle -> Type "Everyone" into box -> Check Names then Ok -> Check "Full Control" box -> OK then Apply
</p>
<br />

<p>
<img src="https://imgur.com/pqlNMcu.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://imgur.com/rWQf6DW.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://imgur.com/qr5hotT.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next, go back to the osTicket website in your web browser and click Continue. Fill out "System Settings" section and "Admin User" section and write the contents down for later use. Before filling out the rest, download HeidiSQL from the installaton files. CLick next on everything and install, when thats done click "New" on the bottom left. Type "root" for User and "Password1" for Password then click Open. Next, right click on "Unnamed" -> Create New -> Database -> Name: osTicktet -> Ok
</p>
<br />

<p>
<img src="https://imgur.com/2M4hTmK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Now, fill out the last section and click "Install Now". Hooray! you've installed osTicket!
</p>
<br />

<p>
<img src="https://imgur.com/TdrPB3E.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Last step is the clean up. Delete C:\inetpub\wwwroot\osTicket\setup and set permissions to “Read” only for C:\inetpub\wwwroot\osTicket\include\ost-config.php

</p>
<br />
