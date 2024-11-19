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

<h1>STEPS FOR OSTICKET PREREQS AND INSTALLATION</h1>


<h2>1. Creating the Virtual Machine in Azure</h2>
A virtual machine named osticket-vm was created in Microsoft Azure. This serves as the environment where osTicket will be installed and run.

<h2>2. Setting Up IIS and PHP Environment</h2>
IIS (Internet Information Services) was installed and configured to host web applications.
CGI (Common Gateway Interface) was enabled to allow IIS to run dynamic scripts, allowing osTicket’s PHP-based functionality.
PHP Manager for IIS and the Rewrite Module were installed. The PHP Manager enables IIS to run PHP scripts (necessary for osTicket), while the Rewrite Module ensures clean and functional URLs.

<h2>3. Installing PHP and Supporting Files</h2>
A folder was created on the C: drive to store PHP files (PHP-7.38...). These files include the core PHP language libraries needed to run osTicket.
The VC-redist.x86 file was installed to provide necessary Microsoft Visual C++ runtime libraries, ensuring osTicket can run correctly.

<h2>4. Installing MySQL and Setting Up the Database</h2>
MySQL was installed to provide the database where osTicket will store its data (like user accounts and ticketing information).
A new database named "osTicket" was created using HeidiSQL for the backend data storage.

<h2>5. Final Configuration of osTicket</h2>
The osTicket files were extracted, and the ‘upload’ folder was renamed to “osTicket” and placed in the wwwroot directory.
IIS was configured to recognize PHP and required PHP extensions (like php_imap.dll, php_opcache.dll) were enabled.
Permissions were set on the ost-sampleconfig.php file, renaming it to ost-config.php and granting full control for installation.
After completing the setup, osTicket's installer was accessed via the browser, and the MySQL database was updated with the necessary data.

