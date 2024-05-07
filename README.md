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

<h2>Installation Steps</h2>

<p>
1.)	After creating the virtual machine (VM), copy the public IP address from Azure.
</p>

<p>
<img src="https://imgur.com/ePjRQJk.png" height="80%" width="80%" />
</p>
<p>
2. Open Remote Desktop Connection, paste the copied IP address, and log in using the credentials created when making the VM. 
</p>
<br />

<p>
<img src="https://imgur.com/urB4Nd7.png" height="30%" width="30%" /> <img src="https://imgur.com/IvoBVgv.png" height="30%" width="30%" />
</p>
<p>
3. Once the virtual machine is connected, go to Control Panel>Programs>Turn Windows features on or off. On the pop-up screen, scroll down to the Internet Information Services folder and select the checkbox beside it to enable it. Also, check World Wide Web Services and Application Development Features.
</p>
<br />

<p>
<img src="https://imgur.com/hR39gdv.png" height="80%" width="80%"/>
</p>
<p>
4. Expand Application Development Features and click the checkbox beside CGI. Then Expand Common HTTP Features and ensure all the folders are checked under it. 
</p>
<br />

<p>
<img src="https://imgur.com/IY6zhCw.png" height="30%" width="30%" /> <img src="https://imgur.com/IvoBVgv.png" height="30%" width="30%" />
</p>
<p>
NOTE: To verify that IIS was successfully installed, enter 127.0.0.1 on the browser. It should load the screen below.
</p>

<br/>

<p>
<img src="https://imgur.com/dsXL6XK.png" height="80%" width="80%"/>
</p>
<p>
5. Download the PHP Manager for IIS from the installation files. Run the installer. On the pop-up screen, select Next>I agree>Next>Close.
6. Download and install the Rewrite Module. On the prompt agree to the user terms, select Install>Finish.
7. Create a folder in Windows Drive C called PHP.
8. Download PHP 7.3.8 the Installation Files, and unzip the contents into C:\PHP

</p>

<br/>

<p>
<img src="https://imgur.com/gOQJKly.png" height="80%" width="80%"/>
</p>
<p>
9. Download and install the VC_redist.x86.exe from the installation files. On the prompt agree to the user terms, select Install>Finish.
10. Download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi) On the prompt select Next then agree to the license agreement. Select Next>Standard Configuration>Next. Make the root password Password1 then select Next>Execute>Finish. 

Note the username is root.

</p>

<br/>

<p>
<img src="https://imgur.com/KuWeMbf.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
11. From the start menu, search for IIS, right-click on it then select run as administrator. Open PHP manager then on the popup screen, select Register new PHP version. From the PHP folder you created, select the php-cgi file then select open. Next, click on Restart on the right side of the screen under actions.
</p>

<p>
<img src="https://imgur.com/YhhuegS.png" height="30%" width="30%"/> <img src="https://imgur.com/7b4Vevd.png" height="30%" width="30%" />
</p>
<p>
12. Download osTicket v1.15.8 from the Installation Files Folder. Extract the files then go to Windows C Drive>inetpub>wwwroot then copy the uploads folder to the root folder in inetpub. Rename this upload folder to "osTicket". Then restart ISS. </br>
14.) On IIS Manager, under Connections, go to Sites>Default>osTicket. On the right, click “Browse *:80”

</p>

<p>
<img src="https://imgur.com/urB4Nd7.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
15. The next step is to enable the extensions for osTicket. Go to IIS>Sites>Default>osTIcket>PHP Manager>Enable or disable extensions. Enable php_imap.dll, php_intl.dll and php_opcache.dll.
</p>

<p>
<img src="https://imgur.com/J1g5Sxk.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>

<p>
<img src="https://imgur.com/BrfR6dp.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
