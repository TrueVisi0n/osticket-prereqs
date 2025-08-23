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

- Apache/Litespeed/IIS Webserver
- PHP version 8.0 or above
- MySQL version 5.5 or above

<h2>Recommended Install Links</h2>

- Install folder: [Download](https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD)

<h2>Installation Steps</h2>

<p>
1) Navigate to Control Panel\Programs, select "Turn Windows features on or off", select "Internet Information Services", hit "OK"
</p>
<p>
<img src="https://imgur.com/1d7A7zx.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
2) Download and extract the files 
</p>
<p>
<img src="https://imgur.com/IWW4Eht.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
3) Install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi) and install the Rewrite Module (rewrite_amd64_en-US.msi)
</p>
<p>
<img src="https://imgur.com/0tpT3cx.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
4) Create the directory "C:\PHP"
</p>
<p>
<img src="https://imgur.com/SOV5mIN.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
5) From the “osTicket-Installation-Files” folder, extract php-7.3.8-nts-Win32-VC15-x86.zip into the “C:\PHP” folder 
</p>
<p>
<img src="https://imgur.com/bpSqJkc.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
6) From the “osTicket-Installation-Files” folder, Install VC_redist.x86.exe
</p>
<p>
<img src="https://imgur.com/TS5CbZN.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<p>
7) From the “osTicket-Installation-Files” folder, Install MySQL 5.5.62-win32.msi
</p>
<p>
<img src="https://imgur.com/8q4BEhp.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Use "Typical" setup, Launch Configuration Wizard, Select "Standard" configuration, **⚠️ Important: Set Username and Password to "root"**
</p>

<br />
<p>
8) Register PHP from within IIS by selecting "PHP Manager", then select "Register new PHP version", path to C:\PHP\php-cgi.exe
</p>
<br />

<br />
<p>
9) Install osTicket by unzipping "osTicket-v1.15.8.zip" and copy the "upload" folder into "C:\inetpub\wwwroot" 
</p>
<br />

<br />
<p>
10) Rename "upload" to "osTicket" 
</p>
<br />

<br />
<p>
11) Reload IIS by selecting "restart" on the webserver 
</p>
<br />

<br />
<p>
12) In IIS navigate to [computer name] > Sites > Default Web Site > osTicket, select "PHP Manager", click "enable or disable an extension", enable "php_imap.dll", "php_intl.dll", and "php_opcache.dll"
</p>
<br />

<br />
<p>
13) Navigate to C:\inetpub\wwwroot\osTicket\include, rename "ost-sampleconfig.php" to "ost-config.php"
</p>
<br />

<br />
<p>
14) In the properties of "ost-config.php", grant "IIS APPPOOL\osTicket" modify permissions
</p>
<br />

<br />
<p>
15) From the "osTicket-Installation-Files", install "HeidiSQL_12.3.0.6589_Setup"
</p>
<p>
<img src="https://imgur.com/k2428SI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<br />

<br />
<p>
16) In HeidiSQL, select "new", set User and Password to "root", select "open"
</p>
<br />

<br />
<p>
17) Right-click "Unnamed", select "create new > database", name database "osTicket", hit "OK"
</p>
<br />

<br />
<p>
17) Right-click "Unnamed", select "create new > database", name database "osTicket", hit "OK"
</p>
<br />

<br />
<p>
18) In IIS navigate to [computer name] > Sites > Default Web Site > osTicket, select "Browse*.80"
</p>
<br />

<br />
<p>
19) Finish the installation setup in osTicket. Hit "Install Now"
<ul>
Database Settings:
<li>MySQL Database: osTicket</li>
<li>MySQL Username: root</li>
<li>MySQL Password: root</li>
</ul>
</p>
<br />

<br />
<p>
20) Navigate to C:\inetpub\wwwroot\osTicket\include, in the properties of "ost-config.php", switch "IIS APPPOOL\osTicket" permission from "modify" to "read"
</p>
<br />
