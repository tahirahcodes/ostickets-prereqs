<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Azure Tenant
- Active Subscription
- Create Resource Group
- Create Virtual Machine
- Enable IIS
- Install Web PLatform Installer
- Install MySQL and setup username and password
- Install Miscrosoft Visual C++ 2009 Redistributable Package
- Configure permissions and Install osTicket
- Installation Files: https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6

<h2>Installation Steps</h2>


1. After creating the virtual machine (VM), copy the public IP address from Azure.


<p>
<img src="https://imgur.com/ePjRQJk.png" height="80%" width="80%" />
</p>
</br>
<p>
2. Open Remote Desktop Connection, paste the copied IP address, and log in using the credentials created when making the VM. 
</p>

<p>
<img src="https://imgur.com/urB4Nd7.png" height="40%" width="40%" /> <img src="https://imgur.com/IvoBVgv.png" height="35%" width="35%" />
</p>

</br>

<p>
3. Once the virtual machine is connected, go to Control Panel>Programs>Turn Windows features on or off. On the pop-up screen, scroll down to the Internet Information Services folder and select the checkbox beside it to enable it. Also, check World Wide Web Services and Application Development Features.
</p>

<p>
<img src="https://imgur.com/hR39gdv.png" height="50%" width="50%"/>
</p>

</br>
<p>
4. Expand Application Development Features and click the checkbox beside CGI. Then Expand Common HTTP Features and ensure all the folders are checked under it. 
</p>

<p>
<img src="https://imgur.com/IY6zhCw.png" height="40%" width="40%" /> <img src="https://imgur.com/WjyZoUv.png" height="40%" width="40%" />
</p>

<p>
NOTE: To verify that IIS was successfully installed, enter 127.0.0.1 on the browser. It should load the screen below.
</p>

<br/>

<p>
<img src="https://imgur.com/dsXL6XK.png" height="80%" width="80%"/>
</p>

5. Download the PHP Manager for IIS from the installation files. Run the installer. On the pop-up screen, select Next>I agree>Next>Close.



6. Download and install the Rewrite Module. On the prompt agree to the user terms, select Install>Finish.



7. Create a folder in Windows Drive C called PHP.
</p>


8. Download PHP 7.3.8 the Installation Files, and unzip the contents into C:\PHP



<p>
<img src="https://imgur.com/gOQJKly.png" height="50%" width="50%"/>
</p>


9. Download and install the VC_redist.x86.exe from the installation files. On the prompt agree to the user terms, select Install>Finish.


10. Download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi) On the prompt select Next then agree to the license agreement. Select Next>Standard Configuration>Next. Make the root password Password1 then select Next>Execute>Finish. 

Note the username is root.


<p>
<img src="https://imgur.com/KuWeMbf.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
</p>

</br>


11. From the start menu, search for IIS, right-click on it then select run as administrator. Open PHP manager then on the popup screen, select Register new PHP version. From the PHP folder you created, select the php-cgi file then select open. Next, click on Restart on the right side of the screen under actions.


<p>
<img src="https://imgur.com/YhhuegS.png" height="60%" width="60%"/> <img src="https://imgur.com/7b4Vevd.png" height="35%" width="35%" />
</p>

<p>
12. Download osTicket v1.15.8 from the Installation Files Folder. Extract the files then go to Windows C Drive>inetpub>wwwroot then copy the uploads folder to the root folder in inetpub. Rename this upload folder to "osTicket". Then restart ISS. 

</br>
13. On IIS Manager, under Connections, go to Sites>Default>osTicket. On the right, click “Browse *:80”

</p>

<p>
<img src="https://imgur.com/vnK3prU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>

<p>
14. The next step is to enable the extensions for osTicket. Go to IIS>Sites>Default>osTIcket>PHP Manager>Enable or disable extensions. 
</p>

<p>
<img src="https://imgur.com/LQ5IPxy.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
</p>

<p>
Enable php_imap.dll, php_intl.dll and php_opcache.dll.
</p>

<p>
<img src="https://imgur.com/LQ5IPxy.png" height="50%" width="50%" alt="Disk Sanitization Steps"/>
</p>

<p>
15. Open Windows C Drive then go to inetpub>wwwroot>osTicket>include then rename ost-sampleconfig.php to ost-config.php
Right click ost-config.php then go to properties. Select Security then Advance, and disable the inheritance. Select Remove all.
</p>

<p>
<img src="https://imgur.com/18LQrfN.png" height="50%" width="50%" />
</p>

<p>
16. Next select Add>Principal then enter <strong>everyone</strong> in the textbox and select Check Names. Ensure all the checkboxes under Basic permissions are selected then click Apply>Ok.
</p>

<p>
<img src="https://imgur.com/7bLYoQa.png" height="50%" width="50%" /> <img src="https://imgur.com/OC4enCG.png" height="40%" width="40%" />
</p>

<p>
17. From the Installation files, download and install Heidi SQL then run the program. Select New to create a session, enter the username as <strong>root</strong> and the password <strong>Password1</strong>. Next select Open.
</p>

<p>
<img src="https://imgur.com/zIVHa4q.png" height="50%" width="50%" /> 
</p>

</br>

<p>
18. Right-click "Unnamed" to the left, select Create New>Databas, then name the new database osTicket.
</p>

<p>
<img src="https://imgur.com/dy5JlWn.png" height="50%" width="50%" /> <img src="https://imgur.com/lVyg9ha.png" height="35%" width="35%" /> 
</p>

<p>
19. Go to Windsows C Drive>inetpub>wwwroot>osTicket and delete the setup folder. Then set back permissions for the ost-config.php file to read only.
</p>

<p>
20.Open osTicket in the browser, click continue, then fill out the required information. Under the MySQL Database settings, enter the username and password created in Heidi in step 17. Click Continue on the osTicket browser page.
</p>

<p>
<img src="https://imgur.com/gWTPO84.png" height="50%" width="50%" /> 
</p>

<p>
osTicket has been successfully installed.
</p>

<p>
<img src="https://imgur.com/ZtQUfgO.png" height="50%" width="50%" /> 
</p>

<p>
You are now able to login with the username and password you created under Admin User.
</p>

<p>
<img src="https://imgur.com/2K7o3tn.png" height="50%" width="50%" /> 
</p>
