<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
In this lab, I will install osTicket from scratch using the required installation files. Several preparatory steps are necessary before installing the ticketing system. This lab is conducted using a Windows 10 Pro virtual machine created on Azure. The referenced and utilized installation files are provided <a href="https://drive.google.com/drive/u/2/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6">here!</a><br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- MySQL
- Internet Information Services (IIS)
  

<h2>Operating Systems Used</h2>

- Windows 10 Pro</b> (22H2)

<h2>Installation Steps</h2>

<p>
<img src=https://github.com/Joanrpena/osticket-prereqs/assets/131486928/63f15979-39ce-401a-9a26-674146731fcd height="85%" width="85%"/>
</p>
<p>
  Before installing any files, Internet Information Services (IIS) must be enabled for osTicket to be properly configured. To enable IIS, open up the Control Panel > click on Programs > Turn Windows features on or off. Within the following window, scroll down and enable "Internet Information Services" > enable expand Web Management Tools and confirm IIS Management Console is enabled > expand World Wide Web Services > expand Application Development Features > enable CGI and click OK to confirm.
</p>
<br />

<p>
  <img src=https://github.com/Joanrpena/osticket-prereqs/assets/131486928/360c6525-d340-4212-9f9a-c46b4e5a908e height="85%" width="85%"/>
</p>
<p>
  After IIS is enabled, open the installation files folder provided at the beginning section <a href="https://drive.google.com/drive/u/2/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6">here</a>, and install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi) followed by installing Rewrite Module (rewrite_amd64_en-US.msi) 
</p>
<br />

<p>
<img src="https://github.com/Joanrpena/osticket-prereqs/assets/131486928/c557e363-199a-4656-a803-9e9b1461b083" height="85%" width="85%" />
</p>
<p>
  Create a new folder called "PHP" on the Windows (C:) drive. This folder is where the contents from the PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) files will be unzipped. You can right click the file > Select "Extract All" > click "Browse" and browse to C:\PHP to extract the contents.
</p>
<br />

<p>
<img src="https://github.com/Joanrpena/osticket-prereqs/assets/131486928/7338a3c6-9e21-4a2c-bdcf-6028d20e88ba" height="85%" width="85%"/>
</p>
<p>
  For the next step, install VC_redist.x86.exe from the installation files, be sure to agree to the license terms and conditions before clicking install. Press close after installation is complete. 
</p>
<br />

<p>
<img src="https://github.com/Joanrpena/osticket-prereqs/assets/131486928/2daa7d69-dcb7-476c-b7b0-0145444f6b10" height="85%" width="85%" />
</p>
<p>
  Next, install MySQL 5.5.62 (mysql-5.5.62-win32.msi) from the provided installation files. While in the installation wizard, click Agree > Typical install > finally click Install. After installation is finished confirm "Launch the MySQL Configuration Wizard" is highlighted and press Finish.
</p>
<img src="https://github.com/Joanrpena/osticket-prereqs/assets/131486928/9a6f9a4d-6369-4af9-b54f-a3a2567123be"
 height="85%" width="85%" />
<p>
  Once the configuration wizard is open press Next > Standard Configuration > Next. Once you arrive at the security options screen you want to configure a secure password for your root account (Default username for root account will be "root"). For the purpose of this lab we will leave "Enable root access from remote machines" unchecked. Click Next > Execute > Finish to close the confirugation wizard.
</p>
<br />

<p>
  <img src="https://github.com/Joanrpena/osticket-prereqs/assets/131486928/336a2f52-01d0-40d8-b16e-16b4eed24e7a" height="75%" width="75%"
/>
  <img src="https://github.com/Joanrpena/osticket-prereqs/assets/131486928/22afa747-18c5-4455-aa75-3e269ea43cf6" height="75%" width="75%"
/>
  <img src="https://github.com/Joanrpena/osticket-prereqs/assets/131486928/5d96c8be-a620-4769-a42a-8be7e656c4bd" height="75%" width="75%"
  />
</p>
<p>
  Before installing osTicket, IIS has to be configured. Type "IIS" in the search bar, right click IIS Manager and run as administrator. Select PHP Manager > Register new PHP Version > Click "..." to browse to the PHP folder created in the C: drive earlier > Click on "php-cgi.exe" and press Ok. After registering the PHP version, reload the server in the management console by right clicking on the host name under Connections panel on the left and stop/start the server.
</p>
<br />

<p>
  <img src="https://github.com/Joanrpena/osticket-prereqs/assets/131486928/409f8412-dcce-46c4-8858-cc946eb991ee" height="85%" width="85%" />
</p>
<p>
  Next, open the osTicket v1.15.8 folder provided in the installation files. Right click on the "upload" folder, and press Copy. On the search bar type: "c:\inetpub\wwwroot" and open up the wwwroot folder. Right click paste on the wwwroot folder. Still in the wwwroot folder, right click on the pasted upload folder and rename it to "osTicket". Reload the IIS Server.
</p>
<br />

<p>
  <img src="https://github.com/Joanrpena/osticket-prereqs/assets/131486928/361b359b-2a6f-4c5e-a7d9-093a8bf1935b" height="75%" width="75%" />
  <img src="https://github.com/Joanrpena/osticket-prereqs/assets/131486928/88c8851d-22bb-463b-9578-c08cf169e631" width="55%" />
  <img src="https://github.com/Joanrpena/osticket-prereqs/assets/131486928/27378424-1831-401f-a635-f5899414753e" height="75%" width="75%" />
</p>
<p>
  Within the IIS console, on the left hand side in the Connections panel, browse to Sites -> Default -> osTicket. Click "Browse *:80" and the installation page for osTicket will now show up. Some extensions are not enabled and they will be enabled with the IIS console before installing osTicket. To do so, click on PHP Manager while in the osTicket menu in IIS. Click on "Enable or disable an extension." Enable the following extentions: php_imap.dll, php_intl.dll, php_opcache.dll.
</p>
<br />

<p>
  <img src="https://github.com/Joanrpena/osticket-prereqs/assets/131486928/09cfc642-3c21-4a09-9729-4d95b3ea9f3d" height="75%" width="75%" />
  <img src="https://github.com/Joanrpena/osticket-prereqs/assets/131486928/82f10eb8-fcba-4189-add9-d5fa922b6221" height="75%" width="75%" />
</p>
<p>
  Before continuing to install osTicket, a file needs to be renamed as well as have its permissions changed. From C:\inetpub\wwwroot\osTicket\include, rename ost-sampleconfig.php to ost-config.php. The newly named ost-config.php will have its permissions changed. Open its Properties > Security > Advanced > change the following permissions: Disable inheritence -> Remove All > Select a principal > under object name type "everyone" then press Check Names" > Assign Full Control then press Ok > Apply > Ok.
</p>
<br />

<p>
  <img src="https://github.com/Joanrpena/osticket-prereqs/assets/131486928/e2c6a75a-723d-44d4-9181-c0d6e77b9f73" height="75%" width="75%" />
  <img src="https://github.com/Joanrpena/osticket-prereqs/assets/131486928/894551ef-5566-4b25-b9f9-7dd637d8cea5" height="75%" width="75%" />
</p>
<p>
 From the installation files, download and install HeidiSQL. Create a new session with HeidiSQL and enter the password used in the installation of MySQL earlier then press Open. Within the new session, right-click on Unnamed and create a new database named osTicket. 
</p>
<br />

<p>
  <img src="https://github.com/Joanrpena/osticket-prereqs/assets/131486928/73c62296-565c-4f19-a6b4-1a2668f1e32e" height="75%" width="75%" />
  <img src="https://github.com/Joanrpena/osticket-prereqs/assets/131486928/6f0f450c-8a38-49ee-b51b-08a2a8e86ef4" height="75%" width="75%" />
</p>
<p>
   We will now go back to our osTicket window, press Continue at the very bottom. You should see the Basic Installation Screen. Under System Settings, and Admin user fill out the information as needed. For the Database Settings, we will leave the first two sections as default, under MySQL Datebase we will enter the database we created with HeidiSQL "osTicket". Username and password will be the same credentials that were used in MySQL and HeidiSQL. Press Install Now after properly entering your database settings.
</p>
<br />

<p>
  <img src="https://github.com/Joanrpena/osticket-prereqs/assets/131486928/eced5eaa-9234-4a01-bf19-21e01daebedf" height="75%" width="75%" />
  <img src="https://github.com/Joanrpena/osticket-prereqs/assets/131486928/374e106c-1aa7-483c-a456-6ca96c068424" height="75%" width="75%" />
</p>
<p>
  osTicket is now installed! Before using osTicket, some clean up must be done. Go back to the C:\inetpub\wwwroot\osTicket folder and delete the "setup" folder. Browse to C:\inetpub\wwwroot\osTicket\include and find the ost-config.php file from earlier. We need to remove Full Control permissions and set them to Read & Excute, and Read.
</p>
<br />

<p>
  <img src="https://github.com/Joanrpena/osticket-prereqs/assets/131486928/21a2683e-16cc-4bd0-89f2-915bcd23a97e" height="80%" width="80%" />
</p>
<p>
  To verify osTicket is installed correctly, open up your internet brower and type in "http://localhost/osTicket/scp/login.php", and log in with your credentials. Success! Tickets can be submitted via "http://localhost/osTicket/" by the end user.
</p>
<br />
<h2>osTicket Installed!</h2>

osTicket is now installed and ready for use. I utilized osTicket to further enhance my understanding of how ticketing systems operate. In IT Support, I collaborate with a team to resolve individuals IT-related issues through the use of a ticketing system. This lab provided an opportunity to set up a ticketing system from scratch, laying the foundation for my future work.


