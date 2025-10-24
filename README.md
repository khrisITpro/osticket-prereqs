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

- Web Server: IIS
- PHP: Version 8.1-8.2
- Database: MySQL 5.0 with a dedicated user with full privileges
- Domain or Static IP
- Install necessary dependencies like C++ Redistributable
- Web-Based Installer with HeidiSQL to finalize installation with MySQL credentials

<h2>Installation Steps</h2>

<p>
First step is to enable Internet Information Services (IIS) with the CGI feature, which allows PHP to work with IIS, using the "Turn Windows features on or off" utility. After enabling IIS, install PHP Manager for IIS and the URL Rewrite Module to manage PHP settings and URL routing. Next extract PHP 7.3.8 into the C:\PHP directory so that IIS can use it to process PHP scripts for osTicket.
<img  src="https://github.com/user-attachments/assets/fe5cc08d-4956-4fc7-afc7-8c92a44b3ca4" />
  <img width="279" height="243" alt="Screenshot 2025-10-23 210138" src="https://github.com/user-attachments/assets/a5cdcfed-d496-4225-ba85-ee267a449508" />

</p>
<p>
We must install the Microsoft Visual C++ distributable x86 as it’s required by PHP and MySQL to run properly. Download the MySQL Installer. During installation, there will be a prompt directing us to create login credentials which are essential to connect the database of osTicket during the web-based setup. 
</p>
<br />

<p>
<img width="561" height="347" alt="Screenshot 2025-10-23 211538" src="https://github.com/user-attachments/assets/663b757f-5874-4739-b40d-13ac36dc5010" />
</p>
<p>
To set up osTicket in IIS, unzip the osTicket-v1.15.8.zip file and move the "upload" folder into C:\inetpub\wwwroot, then rename the folder to "osTicket". Install MySQL 5.5.62-win32.msi and follow along the typical setup and launch the configuration wizard to create a username and password. Next open IIS, browse to the osTicket site, and use PHP Manager to enable required extensions like php_imap.dll, php_intl.dll, and php_opcache.dll. Finally, rename the configuration file to ost-config.php, adjust its permissions by disabling inheritance and granting Everyone full access so osTicket can complete the setup.
<br />

<p>
<img width="327" height="248" alt="Screenshot 2025-10-23 212314" src="https://github.com/user-attachments/assets/402f17a0-2f7d-4cb2-86bf-4f206ea71fa7" />
<img width="618" height="709" alt="Screenshot 2025-10-23 212809" src="https://github.com/user-attachments/assets/7a3bd160-e5ab-4b7f-988d-da7bcbfe7bbe" />


</p>
<p>
Now rename ost-config.php from From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php to C:\inetpub\wwwroot\osTicket\include\ost-config.php. Assign permissions for everyone to all and disable inheritance by removing all. Continue setting up osT in the browser, name it and give it a default email to receive email from customers. From the os installation files, install heidiSQL, create a new session, connect to it and creat a database call "osTicket". Continue with the setup with mySQL and click "install Now!"
 <p>
   <img width="303" height="157" alt="Screenshot 2025-10-23 214110" src="https://github.com/user-attachments/assets/18be0fcb-acff-416e-b3d2-bdf14de70958" />
<img width="618" height="696" alt="Screenshot 2025-10-23 214330" src="https://github.com/user-attachments/assets/9ab749c2-20d3-48d2-bdbb-42e122b682ce" />
<img width="396" height="308" alt="Screenshot 2025-10-23 214624" src="https://github.com/user-attachments/assets/a80eda37-a960-4258-9fe2-f592378513fb" />

</p>
<br />
