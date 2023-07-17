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

Installation of:

- Windows OS Internet Information Services
-  PHP manager for IIS along with Rewrite Module.
-  MySQL Database
- Visual C++ Redistributable package
- HeidiSQL
<h2>Installation Steps</h2>

<p>

![WINDOWS IIS](https://github.com/wildenspm/osticket-prereqs/assets/139749960/1fbac8d8-794b-4f48-a9bf-aafdbd71f78d)




</p>
<p>
First things first, let's enable IIS with CGI and Common HTTP Features and install the IIS Management Console. During the installation process, make sure to tick the checkboxes for CGI and Common HTTP Features in the World Wide Web Services -> Application Development Features section. Additionally, enable the IIS Management Console in the Internet Information Services -> Web Management Tools section. We need these features to get things rolling smoothly.


</p>
<br />

<p> 

![PHP DIRECTORY FOLDER 2](https://github.com/wildenspm/osticket-prereqs/assets/139749960/bb730d80-dd14-4ddd-9ff9-1faee71ae2fa)



</p>
<p>
The next step is to install the PHP Manager for IIS. You can find the installation file (PHPManagerForIIS_V1.5.0.msi) and get it set up. Don't forget to also download and install the Rewrite Module (rewrite_amd64_en-US.msi) to enhance our URL rewriting capabilities. To keep things organized, let's create a directory named "C:\PHP" on our system. We'll need it later.

Now, it's time to grab PHP version 7.3.8. You can find the installation files and specifically look for the zip file named php-7.3.8-nts-Win32-VC15-x86.zip. Once downloaded, extract its contents into the "C:\PHP" directory we just created.

For the smooth functioning of PHP, we need to install the Visual C++ Redistributable package. Grab the VC_redist.x86.exe file from the installation files and run it to complete the installation process.


</p>
<br />

<p>

![osTicket 2](https://github.com/wildenspm/osticket-prereqs/assets/139749960/ca74fd99-857a-4b4a-beaf-47f8b1a18888)


</p>
<p>
Now, let's focus on installing MySQL 5.5.62. Locate the installation file (mysql-5.5.62-win32.msi) and run it. While its installing, choose the typical setup option, launch the configuration wizard, select the standard configuration, and set the password as whatever you want. With MySQL set up, it's time to configure osTicket in IIS. Open IIS as an administrator and register PHP from within IIS. To do this, stop and start the IIS server.

You now nned to get osTicket installed. Download the osTicket files from the installation files folder. Extract the contents of the "upload" folder to "c:\inetpub\wwwroot" and rename it to "osTicket". Once that's done, let's reload IIS to make sure everything is in order.

To enable the necessary PHP extensions, open IIS, navigate to sites -> Default -> osTicket, and double-click PHP Manager. Here, we need to enable a few extensions: php_imap.dll, php_intl.dll, and php_opcache.dll. Once that's done, don't forget to refresh the osTicket site in your browser to observe the changes taking effect.

Now, it's time to configure the ost-config.php file. Head to the C:\inetpub\wwwroot\osTicket\include directory and rename the ost-sampleconfig.php file to ost-config.php.

To ensure proper permissions, disable inheritance for the ost-config.php file and assign new permissions. Grant access to Everyone with full control so that everything runs smoothly.

Let's proceed with the osTicket setup. Open your browser and continue setting up osTicket. Provide the necessary information such as the helpdesk name and the default email address for receiving customer emails.

Next, we need to install HeidiSQL. Download the installation files and proceed with the installation. Once installed, launch HeidiSQL. Create a new session using the root user and set the password as what you has set prior. Connect to the session and create a database called "osTicket".You're all set up with osTicket. 

We're almost there! Head back to the osTicket setup. Provide the MySQL database name (root), username (root), and password (Password1) during the setup process. Click "Install Now!" to complete the installation.

You can now verify if it was installed properly by browsing to the help desk login page at http://localhost/osTicket/scp/login.php. This will be the URL your end users will access: http://localhost/osTicket/.
</p>
<br />
