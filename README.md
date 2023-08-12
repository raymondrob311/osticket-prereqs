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

- PHP Manager for IIS
- PHP 7.3.8
- Rewrite Module 
- VC Redist 
- MySQL

<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/gDR1YeD.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<h2>Part 1 (Create Virtual Machine in Azure)</h2>
  
  Create a Resource Group.<br />Create a Windows 10 Virtual Machine (VM) with 2-4 Virtual CPUs.<br /> (When you are creating the VM, let it create a new Virtual Network (Vnet))

</p>
<br />
<p>
<h2>Part 2: Installation</h2><br />
Create an Azure Virtual Machine Windows 10, 4 vCPUs<br />
<b>Name:</b> (whatever you choose. Just be sure to write it down or remember what you named it)<br />
<b>Username:</b> (whatever you chose)<br />
<b>Password:</b> (whatever you chose)<br /><br />

Install / Enable IIS in Windows WITH<br />
CGI and Common HTTP Features<br />
World Wide Web Services -> Application Development Features -><br />
[X] CGI<br />
[X] Common HTTP Features<br />
AND IIS Management Console<br />
Internet Information Services -> Web Management Tools -> IIS Management Console<br />
	[X] IIS Management Console<br /><br />
 <b>Download and install PHP Manager for IIS<br />
 Download and install ReWrite Module<br />
 Create the directory C:/PHP<br />
 Download and install PHP 7.3.8<br />
 Download and install VC redist<br />
 Download and install MySQL<br /></b>
-Typical Setup -><br />
-Launch Configuration Wizard (after install) -><br />
-Standard Configuration -><br />
-(insert password)<br />

<img src="https://i.imgur.com/cvE5FNr.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
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

OsTicket should be installed with no issues now<br />
Browse to your help desk login page: http://localhost/osTicket/scp/login.php <br />

<b>End Users osTicket URL:</b><br />
http://localhost/osTicket/<br />

<b>Clean up</b><br />
-Delete: C:\inetpub\wwwroot\osTicket\setup <br />
-Set Permissions to “Read” only: C:\inetpub\wwwroot\osTicket\include\ost-config.php<br />

<br />
