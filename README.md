<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>

In this lab, I’ll guide you through setting up osTicket from scratch, starting with all the essential installation files. Before we dive into the actual installation, there are a few prep steps we need to tackle. I’m working on a Windows 10 Pro virtual machine hosted on Azure, so everything will be done in that environment. I’ll also point out where to find the installation files we'll be using along the way.






<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Computer)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)





<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Before we can get started with installing osTicket, we need to enable Internet Information Services (IIS) on our local machine. osTicket relies on IIS to run smoothly, so this step is essential. To do this, head over to the Control Panel and find the option for "Programs." From there, click on "Turn Windows Features On or Off." In the list that appears, scroll down to find "Internet Information Services" and expand it. Next, expand "Web Management Tools" and make sure "IIS Management Console" is checked. Then, go to "World Wide Web Services," expand "Application Development Features," and enable "CGI." Finally, click OK to apply the changes. Now, we’re all set to move forward with the osTicket installation!
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Once IIS is up and running, the next step is to get PHP Manager for IIS installed. You’ll find the installer file, PHPManagerforIIS_V1.5.0.msi, in the installation files folder. After that’s done, we’ll need to download and install the Rewrite Module (rewrite_amd64_en-US.msi) to complete the setup. Make sure you install the PHP Manager first, then follow up with the Rewrite Module. These tools are key to making sure osTicket functions properly on our setup.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
With the Rewrite Module installed, it’s time to set up our PHP environment. Start by creating a new folder on your C: drive called `C:\PHP`. This will be the home for all the PHP files we’ll be working with. Next, grab the PHP 7.3.8 zip file (php-7.3.8-nts-Win32-VC15-x86.zip) from the installation files. Once you’ve got it, extract everything from that zip file straight into the `C:\PHP` folder. Now we’re ready to get PHP integrated with IIS.
</p>
<br />

<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

</p>
<p>
Next up, you’ll need to download and install the `VC_redist.x86.exe` file from the installation files. This little program is crucial for ensuring everything runs smoothly, so don’t skip it! Just grab the file and run the installer, and you’ll be all set for the next steps.
</p>
<br/> 

<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
</p>
Next, it’s time to install MySQL 5.5.62. Grab the installer (`mysql-5.5.62-win32.msi`) from the installation files, and let’s get started. When the MySQL setup wizard pops up, agree to the terms, then choose a Typical install and click Install. Once the installation wraps up, the Configuration Wizard will launch. Here, go with the Standard Configuration, and make sure to select "Install As Windows Service" with the option to launch MySQL Server automatically checked. For this lab, we’ll stick with the default credentials: username `root` and password `Password1`. While these are pretty basic and easy to guess, they’ll work perfectly for our purposes here.
</p>
<br/>

<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
</p>
<br/>

Before we dive into installing osTicket, we need to tweak some settings in IIS. First, open IIS as an admin and head over to PHP Manager. Once there, click on "Register new PHP version." When prompted, browse to the PHP folder we set up earlier and select the `php-cgi.exe` file. With that done, make sure to reload the IIS server from the management console to apply the changes. Now, IIS is ready to handle osTicket!


<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
</p>
<br/>

Now it’s time to get osTicket itself set up. Grab osTicket v1.15.8 from the installation files, then extract it. Inside the extracted files, you’ll find a folder named "upload"—go ahead and copy that folder to `c:\inetpub\wwwroot`. Once it’s in place, rename the "upload" folder to "osTicket." After that, give your IIS server a quick reload to make sure everything’s in sync. And just like that, osTicket is ready to be configured!

<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
</p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
</p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
</p>
In the IIS console, navigate to Sites -> Default -> osTicket. Then, click on "Browse *:80," and you should see the osTicket installation page pop up. However, before we proceed with the installation, we need to enable a few PHP extensions. To do this, stay in the osTicket menu in IIS, and click on PHP Manager. From there, select "Enable or disable an extension." Make sure to enable the following extensions: `php_imap.dll`, `php_intl.dll`, and `php_opcache.dll`. These are essential for osTicket to run smoothly.



<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
</p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
</p>
Before we proceed with the osTicket installation, there’s one more task to take care of: renaming a file and adjusting its permissions. Head over to `C:\inetpub\wwwroot\osTicket\include` and find the file named `ost-sampleconfig.php`. Rename it to `ost-config.php`. Next, we need to lock down the permissions on this file. Right-click on `ost-config.php`, go to Properties, and adjust the permissions by disabling inheritance. Remove all existing permissions, then add new permissions for "Everyone" and set them to "Full Control." This step ensures that the file is properly secured before we continue with the installation.


<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
</p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
</p>

Next, let’s set up HeidiSQL to manage our database. Start by downloading and installing HeidiSQL from the installation files. Once it’s up and running, create a new session. When prompted, enter the same password you used during the MySQL installation earlier. After you’re logged in, right-click on "Unnamed" and choose to create a new database. Name this new database "osTicket," and we’ll be all set to link it up with osTicket in the next steps.

<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
</p>

In the osTicket setup window, it’s time to fill in the details to get everything up and running. For the MySQL database, just plug in the same credentials you used earlier with MySQL and HeidiSQL. Once those are in, you’re well on your way to having osTicket fully set up!



<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
</p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
</p>
Congratulations—osTicket is now installed! But before you start using it, we need to do a little cleanup. First, go to `C:\inetpub\wwwroot\osTicket` and delete the `setup` folder. Then, head back to `C:\inetpub\wwwroot\osTicket\include` and adjust the permissions on the `ost-config.php` file. It’s time to tighten things up: remove the full access permissions for "Everyone" and switch it to "Read" only. This will keep your setup secure as you start using osTicket.
