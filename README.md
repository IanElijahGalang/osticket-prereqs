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
Action: Create a virtual machine (VM) in Microsoft Azure titled "osticket-vm".<br>
<br>Purpose: This VM will be used as the environment for hosting and installing osTicket. 
<img width="1512" alt="vm-azure" src="https://github.com/user-attachments/assets/3d1e6925-9743-4ae0-9430-97638f358d43">

<h2>Step 2: Extract Installation Files and Enable IIS with CGI</h2>
Action:
Extract the osTicket installation files into the VM.
Install IIS (Internet Information Services), which is a web server for hosting web applications.
Enable CGI (Common Gateway Interface) on IIS.<br>
<br>Purpose:
IIS will host the osTicket web application.
CGI allows IIS to run dynamic scripts, such as PHP, needed for osTicket to work properly. Without CGI, IIS would only be able to serve static pages.
<img width="1512" alt="CGI Installation" src="https://github.com/user-attachments/assets/f8cc8257-3b0b-4b72-ac36-47ab9e926870">

<h2>Step 3: Install PHP Manager for IIS and the Rewrite Module</h2>
Action:
Install PHP Manager for IIS.
Install the URL Rewrite Module for IIS.<br>
<br>Purpose:
PHP Manager allows IIS to run PHP, which osTicket is built with.
The Rewrite Module enables clean and user-friendly URLs for osTicket, improving both SEO and usability.


<h2>Step 4: Create a PHP Folder and Extract PHP Files</h2>
Action:
Create a folder on the C: drive to store the PHP files.
Extract the PHP-7.38 files into this folder.<br>
<br>Purpose: These PHP files are necessary for running osTicket. They provide the core PHP language support for dynamic content processing.
<img width="1003" alt="PHP folder w:  PHP Files " src="https://github.com/user-attachments/assets/831214b6-ea83-4f3b-b6a0-0eb2b964ac2c">

<h2>Step 5: Install VC-redist.x86</h2>
Action: Install the VC-redist.x86 file.<br>
<br>Purpose:
This package installs the necessary Microsoft Visual C++ Runtime libraries that osTicket requires to function properly on your computer.
Without this, osTicket might not run or may experience errors related to missing runtime components.

<h2>Step 6: Install MySQL</h2>
Action: Install MySQL on the server to create the database for osTicket.
Set the root password as “root”.<br>
<br>Purpose: MySQL will be used to store all osTicket data, including user accounts, ticket information, and other backend data necessary for the system to operate.
<img width="499" alt="mySQL configuration" src="https://github.com/user-attachments/assets/004731a5-bc44-4935-8c69-b9514649688d">

<h2>Step 7: Open IIS and Configure PHP</h2>
Action: Open Internet Information Services (IIS) as an administrator.
Configure IIS to be aware of the PHP installation.<br>
<br>Purpose: Ensures that IIS can handle PHP scripts and serve dynamic content from osTicket.
<img width="1002" alt="Register PHP on IIS" src="https://github.com/user-attachments/assets/bea58c93-1c34-4372-a921-2472f54fef97">

<h2>Step 8: Extract osTicket Files and Configure Directories</h2>
Action:
Extract the osTicket files from the installation folder.
Rename the ‘upload’ folder to "osTicket".<br>
Move the "osTicket" folder into the wwwroot folder, located under inetpub on the C: drive.
<br>Purpose: Ensures that the osTicket files are in the correct directory for IIS to serve them.
<img width="782" alt="osticket-installation-files" src="https://github.com/user-attachments/assets/e88b99bd-074b-4246-9914-6624b7e74263">

<h2>Step 9: Configure IIS for osTicket</h2>
Action:
In IIS, navigate to Sites > Default > osTicket.
Click *Browse :80 to open the osTicket installer in the browser.
Enable the required PHP extensions in the PHP Manager for IIS:
php_imap.dll
php_intl.dll
php_opcache.dll<br>
<br>Purpose:
The extensions are necessary for osTicket to handle email functionality, internationalization, and performance optimization.
Ensures that osTicket's web interface is properly loaded in the browser.
<img width="799" alt="Enable PHP Extensions" src="https://github.com/user-attachments/assets/22624f6f-3b47-4fe1-9a6c-b6e50ff81256">
<img width="999" alt="osTicket installer updated" src="https://github.com/user-attachments/assets/2b989e38-7587-4091-a3fd-dcccd2064c71">

<h2>Step 10: Change Config File and Set Permissions</h2>
Action:
Rename ost-sampleconfig.php to ost-config.php.
Assign full control permissions to everyone for this file.<br>
<br>Purpose: The config file holds important settings for osTicket. Setting the proper permissions ensures that the installation process can complete without permission errors.
<img width="790" alt="config" src="https://github.com/user-attachments/assets/b6ea4313-abb4-40de-b60f-80be1ce22b51">
<img width="763" alt="assign permissions" src="https://github.com/user-attachments/assets/66d29e35-f626-4fad-8b08-601daf863480">

<h2>Step 11: Finalize osTicket Installation in the Browser</h2>
Action:
Complete the osTicket installation by accessing the installer through the browser.
Follow the installation prompts to configure the osTicket system.<br>
<br>Purpose: This step initializes the osTicket system and sets up the necessary backend and configuration files.
<img width="1512" alt="Ticket Installer Setup" src="https://github.com/user-attachments/assets/05434aa8-a93e-4422-a585-80d9749ce90b">

<h2>Step 12: Install HeidiSQL and Create osTicket Database</h2>
Action: Install HeidiSQL and use it to create a new database named "osTicket".<br>
<br>Purpose: HeidiSQL is a tool used to manage MySQL databases. Creating the osTicket database ensures that osTicket can store and retrieve data from the backend MySQL database.
<img width="934" alt="NewSQL" src="https://github.com/user-attachments/assets/2d371372-8ff9-4e90-bbd4-3c885f9ab55f">

<h2>Step 13: Final Database Setup and Updates</h2>
Action: Once the installation is complete, the osTicket database will be populated with necessary data files.<br>
<br>Purpose: This step ensures that the osTicket database is fully configured with all the required files for the system to operate effectively.
<img width="982" alt="osticket done" src="https://github.com/user-attachments/assets/d52922ed-d5f4-43df-86e1-d89dbecd005d">
<img width="1001" alt="SQL Updated" src="https://github.com/user-attachments/assets/6aefa419-c95f-45a2-979d-783c2afc2847">

