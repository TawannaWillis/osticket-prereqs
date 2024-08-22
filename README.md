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
Before we dive into installing osTicket, we need to tweak some settings in IIS. First, open IIS as an admin and head over to PHP Manager. Once there, click on "Register new PHP version." When prompted, browse to the PHP folder we set up earlier and select the `php-cgi.exe` file. With that done, make sure to reload the IIS server from the management console to apply the changes. Now, IIS is ready to handle osTicket!

