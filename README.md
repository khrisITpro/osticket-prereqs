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
<img src="https://i.imgur.com/HFBKqHa.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Open IIS Manager as an administrator. Register PHP within IIS by configuring the necessary settings. Afterward, restart the server by selecting Restart in the IIS Manager.
</p>
<br />

<p>
<img src="https://i.imgur.com/dUEDOI2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
From the osTicket-Installation-Files folder, unzip osTicket-v1.15.8.zip and copy the upload folder to C:\inetpub\wwwroot. Then, within C:\inetpub\wwwroot, rename the upload folder to osTicket.
</p>
<br />


<p>
<img src="https://i.imgur.com/ofoOo0Z.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Return to IIS Manager and restart the server. Enable the necessary PHP extensions by navigating to Sites -> Default -> osTicket, then double-click PHP Manager. Select "Disable or enable an extension" and enable php_intl.dll, php_opcache.dll, and php_imap.dll. Afterward, refresh the osTicket web server and verify that the Intl Extension is now enabled.
</p>
<br />

<p>
<img src="https://i.imgur.com/JEdBG6b.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Navigate to C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php and rename the file to ost-config.php in the same directory (C:\inetpub\wwwroot\osTicket\include).
</p>
<br />

<p>
<img src="https://i.imgur.com/vFIs9DL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Assign the appropriate permissions to ost-config.php by right-clicking the file and selecting Properties. In the Security tab, disable inheritance, remove all existing permissions, and grant Everyone full access.
</p>
<br />

<p>
<img src="https://i.imgur.com/HZnNtf2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Finally, proceed with the osTicket setup in your browser by clicking Continue. Assign a name to your helpdesk as desired, and select a default email address to receive customer-submitted ticket notifications. Congrats! 
</p>
<br />
