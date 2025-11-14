<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial covers the requirements and installation process for the open-source help desk ticketing system, osTicket.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)
- Files needed to install and configure osTicket: https://drive.usercontent.google.com/download?id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD&export=download&authuser=0

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Azure Virtual Machine 
- osTicket Installation files
- Heidi SQL

<h2>Installation Steps</h2>

<p>
<img width="1709" height="1306" alt="ost" src="https://github.com/user-attachments/assets/b110fe71-40a2-4b9a-bea2-d04f89bd86b6" />
</p>
<p>
Create a resource group in Microsoft Azure named osTicket. Then create a virtual machine within this resource group with a username and password. Use a Windows 10 Pro image for the VM with preferably 2 vCPUs.
</p>
<br />

<p>
<img width="400" height="240" alt="ost1" src="https://github.com/user-attachments/assets/b5a9e87e-48cb-4c61-a0aa-b084149d9ac9" />
</p>
<p>
Next, access the VM via Remote Desktop Protocol (RDP). Use the Public IPv4 address listed in Azure and use it to remote into it from your local machine.
</p>
<br />

<p>
<img width="1119" height="626" alt="ost2" src="https://github.com/user-attachments/assets/aa3ce7e3-a4e2-457d-83d2-452e412e865d" />
</p>
<p>
Once connected, enable IIS with CGI by opening the Control Panel and navigate to Turn Windows Features On or Off. Scroll down to locate Internet Information Services (IIS) and select the checkbox to activate it. Then select World Wide Web Services -> Application Development Features -> [X] CGI
</p>
<br />

<p>

</p><img width="496" height="401" alt="ost3" src="https://github.com/user-attachments/assets/d07f6b17-4b0f-411c-9354-48efdbdb5a68" />
<p>
install PHP Manager, for osTicket to proceed with the setup. (PHPManagerForIIS_V1.5.0.msi)
</p>
<br />

<p>
<img width="488" height="381" alt="ost4" src="https://github.com/user-attachments/assets/bf999b8d-5495-4f9c-bbca-5a8015c76eda" />
</p>
<p>
Within the same folder, install the Rewrite Module to continue configuring the environment. (rewrite_amd64_en-US.msi)
</p>
<br />

<p>
<img width="1140" height="1381" alt="ost5" src="https://github.com/user-attachments/assets/ef288282-3b20-454f-b315-cbcca9a71828" />
</p>
<p>
Create the directory C:\PHP. Unzip the file PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and extract all its contents into the C:\PHP directory.
</p>
<br />

<p>
<img width="483" height="297" alt="ost6" src="https://github.com/user-attachments/assets/153671ec-28f0-4bca-a869-f1c3346643c1" />
</p>
<p>
Install VC_redist.x86.exe from the osTicket Installation folder to ensure the necessary Visual C++ Redistributable components are set.
</p>
<br />

<p>
<img width="489" height="387" alt="ost7" src="https://github.com/user-attachments/assets/fe0b3200-c7c3-41e4-b2f9-cad376671493" />
</p>
<p>
Install MySQL 5.5.62 (mysql-5.5.62-win32.msi) from the osTicket Installation folder to set up the MySQL database server, choose the typcial installation option.
</p>
<br />

<p>
<img width="494" height="373" alt="ost8" src="https://github.com/user-attachments/assets/ce31867f-db38-4bf3-a6ed-113a819c019a" />
</p>
<p>
Launch the configuration wizard after the install, choose standard config, and set username and password to "root".
</p>
<br />

<p>
<img width="1770" height="1010" alt="ost9" src="https://github.com/user-attachments/assets/5de64f0b-8e3f-4569-b79e-72fadd7e5114" />
</p>
<p>
Open IIS Manager as an administrator. Register PHP within IIS by navigating towards the executable file (PHP Manager -> C:\PHP\php-cgi.exe)
. Reload the server by selecting Restart in the IIS Manager.
</p>
<br />

<p>
<img width="1119" height="622" alt="ost9" src="https://github.com/user-attachments/assets/8193e15b-a749-4ddf-bb1c-9949e52839c8" />
</p>
<p>
From the osTicket-Installation-Files folder, unzip osTicket-v1.15.8.zip and copy the "upload" folder to C:\inetpub\wwwroot. Then, within C:\inetpub\wwwroot, rename the upload folder to "osTicket".
</p>
<br />


<p>
<img width="3425" height="1350" alt="ost11" src="https://github.com/user-attachments/assets/c85a5cbe-0c0e-4624-83cc-de60c2c8ed96" />
</p>
<p>
Reload IIS and navigate to sites -> Default -> osTicket On the right, click “Browse *:80”. Enable the necessary PHP extensions by navigating to Sites -> Default -> osTicket, then double-click PHP Manager. Select "Disable or enable an extension" and enable php_intl.dll, php_opcache.dll, and php_imap.dll. Refresh the osTicket web server and verify the changes have been set.
<br />

<p>
<img width="1126" height="633" alt="ost12" src="https://github.com/user-attachments/assets/f18138c0-e43f-4de2-ba24-3a73291832a3" />
</p>
<p>
Navigate to C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php and rename the file to "ost-config.php".
<br />

<p>
<img width="1113" height="825" alt="ost13" src="https://github.com/user-attachments/assets/54b34d37-4470-4faf-8640-10c207932b79" />
<img width="913" height="596" alt="ost14" src="https://github.com/user-attachments/assets/8193ed5b-cc12-4054-9af9-493ad0a98471" />

</p>
<p>
Assign the appropriate permissions to ost-config.php by right-clicking the file and selecting Properties. In the Security tab, disable inheritance, remove all existing permissions, and grant Everyone full access.
</p>
<br />

<p>
<img width="677" height="476" alt="ost15" src="https://github.com/user-attachments/assets/c1b62fe6-d731-4c05-908b-80ef15ae1d45" />
<img width="931" height="590" alt="ost16" src="https://github.com/user-attachments/assets/83e7d5d4-928c-4c5c-a979-ec084de84c2a" />
</p>
<p>
From the osTicket installation folder, install HeidiSQL, create a new session (root/root), connect to the session, and create a database called "osTicket".
</p>
<br />

<p>
<img src="https://i.imgur.com/HZnNtf2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Finally, proceed with the osTicket setup in your browser by clicking Continue. Assign a name to your helpdesk as desired, and select a default email address to receive customer-submitted ticket notifications. Congrats! 
</p>
<br />
