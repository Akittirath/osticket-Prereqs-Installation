<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)
- Windows Server 2022

<h2>List of Prerequisites</h2>

- Azure Virtual Machine
- osTicket Installation files
- Heidi SQL
- PHP

<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/Ksvf29x.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In this first part, we first have to create a resource group in Microsoft Azure. In order to create a resource group, you have to come up with a resource group name and set the region to your preference. Once you have all that set up, you will click review + create. This will show you whether you can create this resource group or not. Once it has passed, you can now create.
</p>
<br />

<p>
<img src="https://i.imgur.com/0uagIHL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Once the resource group has been create, you will then create a VM(Virtual Machine) inside the group. You will choose the destination, name, region, image, availability options and after you will create  a username and password. Once that is finished, confirm and review + create.
</p>
<br />

<p>
<img src="https://i.imgur.com/0pyddWx.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
The easy part is all finished, in this screenshot you will see the details of the VM you have just created. Location, operating systems, size and so on look perfect. Note, we are using 4 CPUs because this project requires more than 1 CPU so I figured 4cpus would be the best bet.
</p>
<br />

<p>
<img src="https://i.imgur.com/4oR5Gct.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Everything looks good, now you will head over to the start menu and type in the search “Remote Desktop Connection” and click on it. If you are a MAC user, you will need to download RDC since mac does not have it pre-installed. Type in or copy your public ip address into the blank section and hit connect.(It will ask you to login, type your login you created during the VM creation part).
</p>
<br />

<p>
<img src="https://i.imgur.com/MMprHRy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Perfect, You’re in! We will now head over to control panel< Programs< Turn windows features on or off< Scroll down to Internet Information Services and check it < Expand it and then expand World Wide Web Services < Scroll to CGI and hit ok.
</p>
<br />

<p>
We will now Install and Enable IIS in Windows with CGI. There will be multiples apps you will need to install so I will provide the link here: Installation Files - Google Drive. Don’t hesitate to click the link, you will need it in order to download osTicket and get it up and running.
<img src="https://i.imgur.com/YJSyCGK.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next step is easy finally, just create a new folder in the C: drive and name it PHP.
Once that is done, you will download PHP 7.3.8 file in the link I have provided. It will be in a ZIP folder so you will need to extract it(Make sure you extract it into the PHP file). It will have some failed files such as C++ redistribution files. So you will need to download Redist.x86, PHP requires this download.

</p>
<br />

<p>
<img src="https://i.imgur.com/YIVBGBM.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
SQL will be the next download, hit standard then install. MySQL Server Instance Configuration Wizard will then pop up. You will create a password for the “User: Root”. I tend to go somewhat an easy password such as “Password01”. You can always be creative but make sure to remember it.
</p>
<br />

<p>
<img src="https://i.imgur.com/FHvVNdb.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
That is all done, we will go to the start menu and type in “iis” which means Internet Information Services. Don’t double click, instead we will “Run-as-administrator”. You will then click PHP Manager and register PHP from within IIS. What we are doing is adding our php file into IIS in order for it to run correctly.
</p>
<br />

<p>
<img src="https://i.imgur.com/tph29Yd.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next download osTicket. Then extract and copy the "upload" folder into c:\inetpub\wwwroot. Afterwards rename the folder to osTicket.
</p>
<br />

<p>
<img src="https://i.imgur.com/dyAxi0l.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
You will then refresh the IIS. Click vm-osTicket on the left, click down arrow on Sites, Click down arrow on Default Web Site, click osTicket and Click Browse *80(http). This will take you to the osTicket Installer website.
</p>
<br />

<p>
<img src="https://i.imgur.com/Gv8q3Wx.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
On the website it will show some PHP extensions are disabled. You will need to go to osTicket PHP Manager to enable those 3 .dll files.
</p>
<br />

<p>
<img src="https://i.imgur.com/LyblajI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Go back into c:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php rename the file to ost-config.php. Assign permissions to ost-config.php Disable inheritance->Remove all New Permissions->Everyone to full access.
</p>
<br />

<p>
<img src="https://i.imgur.com/rnxrZVx.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
The last part of the prereq & Installation! You will create a profile, just fill in the blanks. Noted: Make sure you remember all this. At the bottom of this, you will need to create a SQL database name. In order to do this, you will have to download HeidiSQL>Click next>Next>Install. In HeidiSQL right click new database and type in osTicket. Once that has been created, go back to osTicket Installation and finish up the blanks, once ready, submit the form. You will now get a CONGRATULATION page.
</p>
<br />

<p>
<img src="https://i.imgur.com/Bk1qzM7.png"  height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
