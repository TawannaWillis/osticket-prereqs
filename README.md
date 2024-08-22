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
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
