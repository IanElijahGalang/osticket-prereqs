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
<img width="782" alt="osticket-installation-files" src="https://github.com/user-attachments/assets/ea6f3657-19ae-4ec6-9613-364feac5ac13">

<h2>Step 1: Create a Virtual Machine in Microsoft Azure</h2>
Action: Create a virtual machine (VM) in Microsoft Azure titled "osticket-vm".
Purpose: This VM will be used as the environment for hosting and installing osTicket. 

<h2>Step 2: Extract Installation Files and Enable IIS with CGI</h2>
Action:
Extract the osTicket installation files into the VM.
Install IIS (Internet Information Services), which is a web server for hosting web applications.
Enable CGI (Common Gateway Interface) on IIS.
Purpose:
IIS will host the osTicket web application.
CGI allows IIS to run dynamic scripts, such as PHP, needed for osTicket to work properly. Without CGI, IIS would only be able to serve static pages.

<h2>Step 3: Install PHP Manager for IIS and the Rewrite Module</h2>
Action:
Install PHP Manager for IIS.
Install the URL Rewrite Module for IIS.
Purpose:
PHP Manager allows IIS to run PHP, which osTicket is built with.
The Rewrite Module enables clean and user-friendly URLs for osTicket, improving both SEO and usability.

<h2>Step 4: Create a PHP Folder and Extract PHP Files</h2>
Action:
Create a folder on the C: drive to store the PHP files.
Extract the PHP-7.38 files into this folder.
Purpose: These PHP files are necessary for running osTicket. They provide the core PHP language support for dynamic content processing.

<h2>Step 5: Install VC-redist.x86</h2>
Action: Install the VC-redist.x86 file.
Purpose:
This package installs the necessary Microsoft Visual C++ Runtime libraries that osTicket requires to function properly on your computer.
Without this, osTicket might not run or may experience errors related to missing runtime components.

<h2>Step 6: Install MySQL</h2>
Action: Install MySQL on the server to create the database for osTicket.
Set the root password as “root”.
Purpose: MySQL will be used to store all osTicket data, including user accounts, ticket information, and other backend data necessary for the system to operate.

<h2>Step 7: Open IIS and Configure PHP</h2>
Action: Open Internet Information Services (IIS) as an administrator.
Configure IIS to be aware of the PHP installation.
Purpose: Ensures that IIS can handle PHP scripts and serve dynamic content from osTicket.

<h2>Step 8: Extract osTicket Files and Configure Directories</h2>
Action:
Extract the osTicket files from the installation folder.
Rename the ‘upload’ folder to "osTicket".
Move the "osTicket" folder into the wwwroot folder, located under inetpub on the C: drive.
Purpose: Ensures that the osTicket files are in the correct directory for IIS to serve them.

<h2>Step 9: Configure IIS for osTicket</h2>
Action:
In IIS, navigate to Sites > Default > osTicket.
Click *Browse :80 to open the osTicket installer in the browser.
Enable the required PHP extensions in the PHP Manager for IIS:
php_imap.dll
php_intl.dll
php_opcache.dll
Purpose:
The extensions are necessary for osTicket to handle email functionality, internationalization, and performance optimization.
Ensures that osTicket's web interface is properly loaded in the browser.

<h2>Step 10: Change Config File and Set Permissions</h2>
Action:
Rename ost-sampleconfig.php to ost-config.php.
Assign full control permissions to everyone for this file.
Purpose: The config file holds important settings for osTicket. Setting the proper permissions ensures that the installation process can complete without permission errors.

<h2>Step 11: Finalize osTicket Installation in the Browser</h2>
Action:
Complete the osTicket installation by accessing the installer through the browser.
Follow the installation prompts to configure the osTicket system.
Purpose: This step initializes the osTicket system and sets up the necessary backend and configuration files.

<h2>Step 12: Install HeidiSQL and Create osTicket Database</h2>
Action: Install HeidiSQL and use it to create a new database named "osTicket".
Purpose: HeidiSQL is a tool used to manage MySQL databases. Creating the osTicket database ensures that osTicket can store and retrieve data from the backend MySQL database.

<h2>Step 13: Final Database Setup and Updates</h2>
Action: Once the installation is complete, the osTicket database will be populated with necessary data files.
Purpose: This step ensures that the osTicket database is fully configured with all the required files for the system to operate effectively.

