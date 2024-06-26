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
<img src=https://github.com/Joanrpena/osticket-prereqs/assets/131486928/63f15979-39ce-401a-9a26-674146731fcd/>
</p>
<p>
Before installing any files, Internet Information Services (IIS) must be enabled for osTicket to be properly configured. To enable IIS, open up the Control Panel > click on Programs > Turn Windows features on or off. Within the following window, scroll down and enable "Internet Information Services" > enable expand Web Management Tools and confirm IIS Management Console is enabled > expand World Wide Web Services > expand Application Development Features > enable CGI and click OK to confirm.
</p>
<br />

<p>
  <img src=https://github.com/Joanrpena/osticket-prereqs/assets/131486928/360c6525-d340-4212-9f9a-c46b4e5a908e/>
</p>
<p>
  After IIS is enabled, open the installation files folder provided at the beginning section <a href="https://drive.google.com/drive/u/2/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6">here</a>, and install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi) followed by installing Rewrite Module (rewrite_amd64_en-US.msi) 
</p>

<br />
