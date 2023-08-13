<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
In this tutorial, I will demonstrate how to install osTicket from scratch. There are several programs that are needed to make this process a success before building our ticketing system. You can find those programs <a href="https://drive.google.com/drive/u/2/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6">here.</a> You will also need an <a href="https://portal.azure.com/?quickstart=true#home">Azure account</a> to create resource groups and virtual machines.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- PHP Manager for IIS
- PHP 7.3.8
- Rewrite Module 
- VC Redist 
- MySQL

<h2>Installation Steps</h2>

<p>
<h2>Part 1 (Create Virtual Machine in Azure)</h2>
   
First, create a Windows 10 Virtual Machine with 2-4 Virtual CPUs. While you are creating a virtual machine, create a resource group within the same set up. Be sure to create a name, username and password that you can easily remember for this project.<br />
<img src="https://i.imgur.com/gDR1YeD.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />
<p>
<h2>Part 2: Installation</h2><br />

<b>Install / Enable IIS in Windows WITH</b><br />
Before we start downloading any programs, we need to enable IIS (Internet Information Services). To enable IIS, open the Control Panel. Once the Control Panel window is open, click Programs. Under Programs and Features, select Turn Windows features on or off. From this window, expand Internet Information Services, then expand Web Management Tools. Select IIS Management Console simply by clicking the box next to it. From there, expand World Wide Web Services, expand Application Development Features and enable CGI. Click OK when done.  <br /><br />
 <b>Download and install PHP Manager for IIS<br />
 Download and install ReWrite Module<br /></b>
 You can download these programs from the link provided in the introduction above. Install both of these programs into the virtual machine. After these two programs are installed, create the directory C:/PHP on the Windows (C:) Drive. YOu can do this from the File Explorer. <br />
 <b>Download and install PHP 7.3.8<br />
 Download and install VC redist<br />
 Download and install MySQL<br /></b>
-Typical Setup -><br />
-Launch Configuration Wizard (after install) -><br />
-Standard Configuration -><br />
-(insert password)<br />

<img src="https://i.imgur.com/cvE5FNr.png"/>
</p>
<p>

<b>Open IIS as an Admin<br />
Register PHP from within IIS<br />
Reload IIS (Open IIS, Stop and Start the server)<br />
Install osTicket v1.15.8</b><br />
-Download osTicket from the Installation Files Folder<br />
-Extract and copy “upload” folder to c:\inetpub\wwwroot <br />
-Within c:\inetpub\wwwroot, Rename “upload” to “osTicket”<br />
<b>Reload IIS (Open IIS, Stop and Start the server)</b><br />
<b>Go to sites -> Default -> osTicket</b><br />
-On the right, click “Browse *:80” <br /><br />

<b>Notice that some extensions are not enabled</b><br />
-Go back to IIS, sites -> Default -> osTicket<br />
-Double-click PHP Manager<br />
-Click “Enable or disable an extension”<br />
-Enable: php_imap.dll<br />
-Enable: php_intl.dll<br />
-Enable: php_opcache.dll<br />
-Refresh the osTicket site in your browse, observe the changes<br />

<b>Rename: ost-config.php</b><br />
-From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php <br />
-To: C:\inetpub\wwwroot\osTicket\include\ost-config.php<br />

<b>Assign Permissions: ost-config.php</b><br />
-Disable inheritance -> Remove All<br />
-New Permissions -> Everyone -> All<br />

<b>Continue Setting up osTicket in the browser (click Continue)</b><br />
-Name Helpdesk<br />
-Default email (receives email from customers)<br />
<b>Download and install HeidiSQL.</b><br />
-Open Heidi SQL<br />
-Create a new session, root/Password1<br />
-Connect to the session<br />
-Create a database called “osTicket”<br />

<b>Continue Setting up osticket in the browser</b><br />
-MySQL Database: osTicket<br />
-MySQL Username: (insert username)<br />
-MySQL Password: (insert password)<br />
-Click “Install Now!”<br />

OsTicket should be installed with no issues and is ready to be used. From here, you will learn how tickets are submitted and resolved. It will be great practice for anyone interested in IT support. This will help you resolve and work through any issues that a customer or client might have. Using this system and practicing it several times has helped prepare me for the future. <br />
Browse to your help desk login page: http://localhost/osTicket/scp/login.php <br />

<b>End Users osTicket URL:</b><br />
http://localhost/osTicket/<br />

<b>Clean up</b><br />
-Delete: C:\inetpub\wwwroot\osTicket\setup <br />
-Set Permissions to “Read” only: C:\inetpub\wwwroot\osTicket\include\ost-config.php<br />

<br />
