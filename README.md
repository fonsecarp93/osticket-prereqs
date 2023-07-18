# osticket-prereqs

<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Computer)
- Remote Desktop
- Internet Information Services (IIS)
- [Installation Files](https://drive.google.com/drive/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6?usp=sharing)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- PHP Manager for IIS (Step 3)
- Rewrite Module (Step 3)
- PHP 7.3.8
- VC_redist.x86.exe
- MySQL5.5.62
- osTicket v1.15.8
- HeidiSQL

<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

1.) Create a Windows 10 Virtual Machine (VM) in Microsoft Azure and allow it to create a new Virtual Network (Vnet)
  Note: When creating the VM, create it with 2-4 Virtual CPUs

<img src="https://i.imgur.com/uD8cbnO.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

2.) Install and Enable INternet Information Services in Windows with CGI, Common HTTP Features, and Internet Information Services Management Console.

</p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />

3.) Download and install the PHP Manager for IIS, then the Rewrite Module from the [Installation Files](https://drive.google.com/drive/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6?usp=sharing)
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

4.) Create the directory C:\PHP
  Download zip file PHP 7.3.8 from the [installation files](https://drive.google.com/drive/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6?usp=sharing) and unzip its contents into C:\PHP

  <p></p>
  
5.) Download and install VC_redist.x86.exe, then MySQL5.5.62 from the installation
  NOTE: When installing and setting up MySQL, proceed with the Typical Setup.

</p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

6.) Open Internet Information Services (IIS) as an administrator and register PHP from within it. After doing so, reload IIS.
Install osTicket v1.15.8 from the [installation files](https://drive.google.com/drive/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6?usp=sharing).
    Extract and copy the "upload" folder to c:\inetpub\wwwroot
    <p>
    Within c:\inetpub\wwwroot, rename "upload" to "osTicket"
Reload IIS

7.) Go to sites -> Default -> osTicket, and "Browse *:80"
    When arriving, some extensions are not enabled. We will enable these extensions
  Go to the PHP Manager and enable the following extensions
      php_imap.dll
      php_intl.dll
      php_opcache.dll
  Refresh the osTicket site and all changes should go into effect.

<p></p>
  
8.) Rename: ost-config.php
    From:
      C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
    To:
      C:\inetpub\wwwroot\osTicket\include\ost-config.php

    Assign Permissions: ost-config.php
        Disable inheritance: -> Remove All
        New Permissions: -> Everyone -> All

<p></p>

9.) From the installation files (C:\inetpub\wwwroot\osTicket\include\ost-config.php) download and install HeidiSQL.
    Create a new session (root/Password1) and connect to it
    Create a database called "osTicket"

<p></p>

10.) Continue setting up osTicket in the browser
    Name: Helpdesk
    Default Email
    MySQL Database: osTicket
    MySQL Username: root
    MySQL Password: Password1
  "Install Now"

  osTicket should now be installed with no errors.
</p>
<br />
