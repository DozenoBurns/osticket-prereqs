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

- Windows 11</b> (21H2)

<h2>List of Prerequisites</h2>

- Create an Azure Virtual Machine Windows 10, 4 vCPUs
   -  Name: osticket-vm
   -   Username: labuser
   -    Password: osTicketPassword1!

- Log into the VM with Remote Desktop

   - Within the VM (osticket-vm), download the osTicket-Installation-Files.zip and unzip it onto your desktop. The folder should      be called “osTicket-Installation-Files”
   -  We will use the files in this folder to install osTicket and some of the dependencies.

 - Install / Enable IIS in Windows WITH CGI
   - World Wide Web Services -> Application Development Features -> [X] CGI

   - From the “osTicket-Installation-Files” folder, install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)

    - From the “osTicket-Installation-Files” folder install the Rewrite Module (rewrite_amd64_en-US.msi)

- Create the directory C:\PHP

  -  From the “osTicket-Installation-Files” folder, unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into the “C:\PHP” folder

   -  From the “osTicket-Installation-Files” folder, install VC_redist.x86.exe.

   -  From the “osTicket-Installation-Files” folder, install MySQL 5.5.62 (mysql-5.5.62-win32.msi)
   -  Typical Setup ->
- Launch Configuration Wizard (after install) ->
   - Standard Configuration ->
   - Username: root
   - Password: root

- Open IIS as an Admin

  - Register PHP from within IIS (PHP Manager -> C:\PHP\php-cgi.exe)

   - Reload IIS (Open IIS, Stop and Start the server)

- Install osTicket v1.15.8
   - From the “osTicket-Installation-Files” folder, unzip “osTicket-v1.15.8.zip” and copy the “upload” folder into “c:                \inetpub\wwwroot”
   - Within “c:\inetpub\wwwroot”, Rename “upload” to “osTicket”

    - Reload IIS (Open IIS, Stop and Start the server)

    - Go to sites -> Default -> osTicket
      On the right, click “Browse *:80”


     - Go back to IIS, sites -> Default -> osTicket
       Double-click PHP Manager
     - Click “Enable or disable an extension”
     - Enable: php_imap.dll
     - Enable: php_intl.dll
     - Enable: php_opcache.dll
- Refresh the osTicket site in your browser, observe the changes

   - Rename: ost-config.php
   - From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
   - To: C:\inetpub\wwwroot\osTicket\include\ost-config.php

- Assign Permissions: ost-config.php
   - Disable inheritance -> Remove All
   - New Permissions -> Everyone -> All

- Continue Setting up osTicket in the browser (click Continue)
   - Name Helpdesk
   - Default email (receives email from customers)

   - From the “osTicket-Installation-Files” folder, install HeidiSQL.
- Open Heidi SQL
   - Create a new session, root/root
   - Connect to the session
   - Create a database called “osTicket”

- Continue Setting up osTicket in the browser
  - MySQL Database: osTicket
  - MySQL Username: root
  - MySQL Password: root
- Click “Install Now!”

Congratulations, hopefully it is installed with no errors!
Browse to your help desk login page: http://localhost/osTicket/scp/login.php

- End Users osTicket URL:
  - http://localhost/osTicket/ 

- Clean up
  - Delete: C:\inetpub\wwwroot\osTicket\setup
  - Set Permissions to “Read” only: C:\inetpub\wwwroot\osTicket\include\ost-config.php


<h2>Installation Steps</h2>

<p>
<img width="551" alt="Screenshot osticket installation" src="https://github.com/user-attachments/assets/357eda45-cd33-40eb-b889-979df61b9e7e" />

<img width="721" alt="Screenshot osticket setup IIS" src="https://github.com/user-attachments/assets/95d82462-8a4c-4c03-b82a-bfe76edc7000" />

<img width="551" alt="Screenshot susscessful installation of osticket" src="https://github.com/user-attachments/assets/f594c202-d4e8-4ea1-9e76-747cabd9c57d" />


</p>
<p>
These screenshot's shows the setup process of the osTicket ticketing system on a Microsoft Azure Virtual Machine. It includes VM deployment, web server configuration, and osTicket installation to manage customer support efficiently..
</p>
<br />

<p>
<img width="725" alt="Screenshot Creating roles giving premissions in osticket" src="https://github.com/user-attachments/assets/6f6ab7e3-f9e0-4aae-b746-91235f5f0b25" />

<img width="746" alt="Screenshot creating new department in osTicket" src="https://github.com/user-attachments/assets/e0102480-db50-45e9-b0bd-f8a84b351676" />

<img width="763" alt="Screenshot adding new agents to osticket system" src="https://github.com/user-attachments/assets/8f3fe345-1401-4614-8144-7dc8f65114ff" />


</p>
<p>
These screenshot's shows how to add new agents and create departments in the osTicket system. Administrators can navigate to the "Agents" section to add new support agents and assign roles. Departments can be created under the "Departments" section to organize ticket management efficiently. This helps streamline support operations and improve workflow.
</p>
<br />

<p>
<img width="758" alt="Screenshot created SLA Plans SEV-A,B,C" src="https://github.com/user-attachments/assets/8c9aade6-641c-4f1c-b4e4-09651571654b" />

<img width="733" alt="Screenshot Created new help topics in osticket" src="https://github.com/user-attachments/assets/bf8ffa83-148a-4582-bf1a-eafa22d1b5b6" />

<img width="758" alt="Screenshot created SLA Plans SEV-A,B,C" src="https://github.com/user-attachments/assets/3121b530-3a11-4b25-8bee-93082329b16d" />

<img width="746" alt="Screenshot observing created ticket as help desk user" src="https://github.com/user-attachments/assets/65a1affd-a39a-4f43-8f83-9c56e3e82167" />

<img width="725" alt="Screenshot replying to support tickets " src="https://github.com/user-attachments/assets/3f459cf1-7d67-47ea-8934-204189f88e87" />



</p>
<p>
These screenshot's illustrates the creation of Service Level Agreements (SLAs) categorized into Severity A, B, and C. It shows the process of monitoring simulated help desk tickets, analyzing their urgency, and responding accordingly. Additionally, it demonstrates forwarding tickets to the appropriate department to ensure efficient issue resolution.
</p>
<br />
