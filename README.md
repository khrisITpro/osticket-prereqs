<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial covers the requirements and installation process for the open-source help desk ticketing system, osTicket.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Azure Virtual Machine 
- osTicket Installation files
- Heidi SQL

<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/Iu8EC4s.png" height="80%" width="80%" alt="Disk Sanitization Steps"/> 
</p>
<p>
Create a resource group in Microsoft Azure named osTicket. Then create a virtual machine within this resource group. Use a Windows 10 Pro image for the VM, ensuring it has at least 2 vCPUs. The VM will serve as a space for practice.
</p>
<br />

<p>
<img src="https://i.imgur.com/H2B3g7x.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next, access the VM via Remote Desktop Protocol (RDP). Copy the Public IPv4 address listed in the Azure portal for the VM and use it to establish the RDP connection.
</p>
<br />

<p>
<img src="https://i.imgur.com/2VqhhFo.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Once connected to the VM, enable IIS by opening the Control Panel and navigating to Turn Windows Features On or Off. Scroll down to locate Internet Information Services (IIS) and select the checkbox to activate it.
</p>
<br />

<p>
<img src="https://i.imgur.com/jdy6kVT.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
From the osTicket Installation folder, locate and install PHP Manager to proceed with the setup.
</p>
<br />

<p>
<img src="https://i.imgur.com/BraQ2Sp.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Within the same folder, install the Rewrite Module to continue configuring the environment.
</p>
<br />

<p>
<img src="https://i.imgur.com/3G7QEou.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<img src="https://i.imgur.com/BJ7pQXn.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Create the directory C:\PHP. Unzip the file PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and extract all its contents into the C:\PHP directory.
</p>
<br />

<p>
<img src="https://i.imgur.com/vnapOUJ.jpeg" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Install VC_redist.x86.exe from the osTicket Installation folder to ensure the necessary Visual C++ Redistributable components are in place.
</p>
<br />

<p>
<img src="https://i.imgur.com/6Ni4PkJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Install MySQL 5.5.62 (mysql-5.5.62-win32.msi) from the osTicket Installation folder to set up the MySQL database server.
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
