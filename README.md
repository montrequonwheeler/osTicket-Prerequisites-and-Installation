<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This walkthrough outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop (Microsoft Remote Access in the App Store for MAC users)
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Setup a VM in Azure
- Install the osTicket requirements from the link provided https://docs.google.com/document/d/12QH7yrsaiUfYNOgZK7KgTSZQSJ-HYTSVcGFildWMRig/edit#bookmark=id.cajb4ktub1km

<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/frBCLna.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
First create a resource group by typing resource group in the searchbar in the top middle, the same will be done for the virtual machine with the same resource group, and allow it to create a new vnet.
</p>
<br />

<p>
<img src="https://github.com/montrequonwheeler/osticket-prereqs/assets/127397594/3604ef6c-ffc3-4985-b9e2-89697b8994ab" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next we will login into the VM through Remote Desktop and install / enable IIS along with the other prerequisites for osTicket. IIS is essentially a web service that allows the CPU to serve up websites. Since osTicket runs out of a web site, we need to configure IIS. As presented in the snippet above, open the control panel -> programs -> Windows features on and off, you'll find and check the box for Internet Information Service -> World Wide Web -> Application Development Features -> check the box for CGI. Below should be Common HTTP Features and we'll check that as well. 
</p>
<br />

<p>
<img src="https://github.com/montrequonwheeler/osticket-prereqs/assets/127397594/0070d916-f0da-4e74-9a5e-6c9c7582e67a" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
To test if our web servers are working correctly, we can open a new tab and type 127.0.0.1 which is a local host or loopback like the video below. We needed to install CGI with IIS because it lets us install PHP Manager and osTicket runs off of PHP. So we have to install a web server (IIS) with PHP on the CPU. Next up is to download and install, PHP Manager for IIS, Rewrite Module, PHP, VC_redist, MySQL, osTIcket, and HeidiSQL with a few special instructions.
</p>
<br />

<p>
<img src="https://github.com/montrequonwheeler/osticket-prereqs/assets/127397594/e713158d-4150-4b33-9b19-ee91f4cb7a00" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Incase of running into any issues when downlaoding the files for PHP, like the video below choose keep -> keep anyway for the download portion so the contents can be later extracted into the directory C:\PHP we created earlier.
</p>
<br />

<p>
<img src="https://github.com/montrequonwheeler/osticket-prereqs/assets/127397594/3bd8df51-68b1-4d76-92b7-b7319283b4a4" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Now that PHP, VC_redist, and MySQL are installed, next will be to open and run IIS as administrator and register PHP from within IIS and reload IIS. Anytime we make any changes or updates within IIS it is recommended to reload IIS (within IIS, in the top right corner stop and start the server).
</p>
<br />

<p>
<img src="https://github.com/montrequonwheeler/osticket-prereqs/assets/127397594/1868a4cb-c1b4-45c5-bcec-5af41854b29d" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Once PHP Manager is enabled and both VC_redist, and MySQL are installed, next will be to install osTicket and open in the browser.
</p>
<br />

<p>
<img src="https://github.com/montrequonwheeler/osticket-prereqs/assets/127397594/eb77f16b-d543-4be6-9c5b-8b791de8bdee" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
As per instucted in the link above, the fourth to last step will be to assign permissions:ost-config.php as presented in the video below. We're going to allow everyone to have permission for this file because the osTicket installer that's going to run in this browser to manipulate and interact with this file and we're unsure of which user it's going to use to do that.
</p>
<br />

<p>
<img src="https://github.com/montrequonwheeler/osticket-prereqs/assets/127397594/f3b2b48e-fff4-4d5a-8586-4a361e4f3efb" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next will be to install HeidiSQL. In the previous downloads when installing MySQL, it was installing a database on the actual CPU so osTicket can store the application data like tickets and the users. HeidiSQL will allow us to to connect to the SQL server. Then we're going to set up a database the osTicket is going to use.
</p>
<br />

<p>
<img src="https://github.com/montrequonwheeler/osticket-prereqs/assets/127397594/07b9aa2e-1918-4dcb-85c3-20be9c3bbbb4" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
After finshing up the installation for everything, last is to clean up and then finish the post installation set up to practice using osTicket as a admin and end user. 
</p>
<br />

<p>
<img src="https://github.com/montrequonwheeler/osticket-prereqs/assets/127397594/10d7a406-44b6-4847-9846-1d890e36849c" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Now we can move on the post installation of this project.
