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

- computer
- Internet connection


<h2>Installation Steps</h2>

![image](https://github.com/hughscode/osticket-prereqs/assets/147445518/f93981d0-89f9-40b1-8a60-f99c444b3f72)
<p>
Open and creat an account to Microsoft Azure.
</p>
<br />






Installation
 ![image](https://github.com/hughscode/osticket-prereqs/assets/147445518/79359a46-895f-498d-9125-4b408fa59f95)

<p>
Then create a new resource group.
  
![image](https://github.com/hughscode/osticket-prereqs/assets/147445518/fe95473c-fb08-4316-b2f4-4a8a1dbfb42c)
Configure the new resource groups settings such as Azure subscription, name and region of the newly created resource group.


now its time to create a new virtual machine
![image](https://github.com/hughscode/osticket-prereqs/assets/147445518/debf1236-2497-4175-a6ef-9294ff54fe08)


Configure your virtual machines settings.

![image](https://github.com/hughscode/osticket-prereqs/assets/147445518/d19968f3-ea49-464c-8c2e-7cbef8e7a6de)


Imput username and password for virtual machine and click review + create.

(https://github.com/user-attachments/assets/cfd1c751-64c3-475b-b851-8f1a63c3dbb4)


Creat a new PC on Microsft Remote Desktop using the public IP address provided by the newly created virtual machine on Microft Azure
(https://github.com/user-attachments/assets/abbaffa2-6ced-421e-9d63-21689550c48f)


Download and extract OsTicket intallation files from [
](https://docs.google.com/document/d/1DyjX8LeVU98LjhXO2t2K2F0aHywI2N9GD57T3taO5qo/edit?pli=1&tab=t.0)

(https://github.com/user-attachments/assets/58fd54ee-0434-482b-800d-31f49ed3ef9d)
(https://github.com/user-attachments/assets/60dd14c7-4426-44aa-8910-9be1779ffc1a)


Install / Enable IIS in Windows WITH CGI within the virtual computer
(https://github.com/user-attachments/assets/5e6278b4-bd96-42de-bb9a-f4d9dde3b020)


From the “osTicket-Installation-Files” folder, install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)
(https://github.com/user-attachments/assets/dfa1c326-3774-42a1-afdc-49646729dc31)


  From the “osTicket-Installation-Files” folder install the Rewrite Module (rewrite_amd64_en-US.msi)<p>
  (https://github.com/user-attachments/assets/a7cd55f4-3815-4bad-8e25-5e979bf5fe48)


Create the directory C:\PHP
(https://github.com/user-attachments/assets/623e771d-eb12-4819-91aa-03f68d104550)


From the “osTicket-Installation-Files” folder, unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into the “C:\PHP” folder
(https://github.com/user-attachments/assets/e9421784-463c-42be-9126-7316898946cf)


From the “osTicket-Installation-Files” folder, install VC_redist.x86.exe.
(https://github.com/user-attachments/assets/2aeb92a3-65a0-462c-9a79-25c391c2f6e5)


From the “osTicket-Installation-Files” folder, install MySQL 5.5.62 (mysql-5.5.62-win32.msi)
Typical Setup ->
Launch Configuration Wizard (after install) ->
Standard Configuration ->
Username: root
Password: root
(https://github.com/user-attachments/assets/dbea5b6f-c155-40ea-83e8-4af193f9d3af)


Open IIS as an Admin
(https://github.com/user-attachments/assets/c3b2aeac-b55a-438e-8243-13840e969799)


Register PHP from within IIS (PHP Manager -> C:\PHP\php-cgi.exe)
(https://github.com/user-attachments/assets/1e11d1f6-3d0f-44bd-9886-a85b4f89cab6)


Reload IIS (Open IIS, Stop and Start the server)
(https://github.com/user-attachments/assets/7075e3dd-9d45-4189-b914-cc89d63e4909)


Install osTicket v1.15.8
From the “osTicket-Installation-Files” folder, unzip “osTicket-v1.15.8.zip” and copy the “upload” folder into “c:\inetpub\wwwroot”
Within “c:\inetpub\wwwroot”, Rename “upload” to “osTicket”
Reload IIS (Open IIS, Stop and Start the server)
(https://github.com/user-attachments/assets/8eb91cc2-067d-4cae-a8ac-f763e2484dbc)


Go to sites -> Default -> osTicket
On the right, click “Browse *:80”
(https://github.com/user-attachments/assets/272be9ff-9106-46b5-b431-6cd8e496bd12)


Go back to IIS, sites -> Default -> osTicket
Double-click PHP Manager
Click “Enable or disable an extension”
Enable: php_imap.dll
Enable: php_intl.dll
Enable: php_opcache.dll
Refresh the osTicket site in your browser, observe the changes
(https://github.com/user-attachments/assets/215372b8-6bfa-465f-aae1-e202f6680449)
(https://github.com/user-attachments/assets/58ea2271-c2b8-4a2c-b5a4-51773a3e5ec3)


Rename: ost-config.php
From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
To: C:\inetpub\wwwroot\osTicket\include\ost-config.php
(https://github.com/user-attachments/assets/3e526f5b-a88b-4026-8e53-eec8a15b30d2)


Assign Permissions: ost-config.php
Disable inheritance -> Remove All
New Permissions -> Everyone -> All
(https://github.com/user-attachments/assets/ebfc3afd-da56-484b-8f9f-406607fd1d77)
(https://github.com/user-attachments/assets/020addcd-dbfb-4dce-92ec-85b7fcfa8d86)


Continue Setting up osTicket in the browser (click Continue)
Name Helpdesk
Default email (receives email from customers)
(https://github.com/user-attachments/assets/885c0789-b0e9-4261-b09d-8d6d3c366e90)















</p>

<b
