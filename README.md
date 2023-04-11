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
<img src="https://i.imgur.com/DJmEXEB.png" height="100%" width="100%" alt="Disk Sanitization Steps"/>
</p>
<p>
Part 2 (Installation):
To begin the installation, open the Installation Files. These files will be used to install osTicket and some of the dependencies. Start by installing/Enabling IIS in Windows WITH CGI. Then, download and install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi) and the Rewrite Module (rewrite_amd64_en-US.msi).
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create the directory C:\PHP and download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) from the Installation Files. Unzip the contents into C:\PHP. Next, download and install VC_redist.x86.exe and MySQL 5.5.62 (mysql-5.5.62-win32.msi). During the installation of MySQL, select the Typical Setup, Launch Configuration Wizard (after install), and Standard Configuration. Set the password to Password1.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Open IIS as an Admin and register PHP from within IIS. Reload IIS by stopping and starting the server. Next, install osTicket v1.15.8. Download osTicket from the Installation Files Folder and extract and copy the "upload" folder to c:\inetpub\wwwroot. Within c:\inetpub\wwwroot, rename "upload" to "osTicket". Reload IIS by stopping and starting the server.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Go to sites -> Default -> osTicket and on the right, click "Browse *:80". Note that some extensions are not enabled. Go back to IIS, sites -> Default -> osTicket and double-click PHP Manager. Click "Enable or disable an extension" and enable php_imap.dll, php_intl.dll, and php_opcache.dll. Refresh the osTicket site in your browser to observe the changes.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Rename ost-sampleconfig.php to ost-config.php within C:\inetpub\wwwroot\osTicket\include. Assign Permissions to ost-config.php by disabling inheritance, removing all permissions, and adding permissions for Everyone to have All access.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Continue setting up osTicket in the browser by clicking "Continue". Name your help desk and set up your default email to receive emails from customers. From the Installation Files, download and install HeidiSQL. Open HeidiSQL, create a new session with root/Password1, and connect to the session. Create a database called "osTicket".
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
