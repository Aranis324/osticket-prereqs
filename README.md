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

<h2>List of Prerequisites</h2>

- Azure Virtual Machine
- [PHP Magnager for IIS](https://drive.google.com/file/d/1RHsNd4eWIOwaNpj3JW4vzzmzNUH86wY_/view?usp=share_link)
- [Rewrite Module](https://drive.google.com/file/d/1tIK9GZBKj1JyUP87eewxgdNqn9pZmVmY/view?usp=share_link)
- [VC_redist.x86.exe](https://drive.google.com/file/d/1s1OsGF3-ioO0_9LYizPRiVuIkb3lFJgH/view?usp=share_link)
- [ MySQL](https://drive.google.com/file/d/1_OWh9p7VQLcrB0q_V7qT8yHl0xo5gv7z/view?usp=share_link)

<h2>Installation Steps: Prerequisite</h2>

<p>
<img src="https://github.com/Aranis324/osticket-prereqs/assets/163223660/ce3500cf-5f8d-4283-8a65-4c13059d68f0"/>
</p>
<p>
The first steps you need to begin installing osTicket is to have an active Azure Virtural Machine installed and a Resource Group open. You'll have to play around with your reigonal location in order to find a size option that is applicable to you. Also make sure that you choose Windows 10 Pro in the Image section. When you have your selecions settled, just make a username and password, let Azure create its own subnet and IP, and we can move on to the next step.
<br />

<p>
<img src="https://github.com/Aranis324/osticket-prereqs/assets/163223660/3395d7f7-255c-496b-ad08-0afc74d4a17e"/>
</p>
<p>
After your done making the VM, we have to set up IIS for our VM. Open up a Remote Desktop Connection on your computer, then copy and paste the IP Address of your VM into there, and use the sign in you made for your it. Then open up the control panel in your VM, and go to Programs, Turn On and Off Programs, then drop down Internet Inforamtion Services, World Wide Web Services, Application Development Features and check on CGI and Common HTTP Features. Then drop down Web Management Tools and check on ISS Managment Console. Now go back and double check if you have everything on before moving on to the next step
</p>
</p>
<br />

<p>
<img src="https://github.com/Aranis324/osticket-prereqs/assets/163223660/360ffbce-36a5-4249-af2b-76072c874394"/>
</p>
<p>
Once you have evertyhing above set up, we need to install software to help us run osTicket. Up in the prerequisites are all the instalation files requried for this process, of which our first batch of installation will be PHP Manager for IIS and the Rewrite Module. Noting fancy or specific to download these, so once thats done we can move on to the next step. In your C Drive, create a directory called C:\PHP and then download the following 
https://drive.google.com/file/d/1snNMtLdCOpMtkCyD4mvl9yOOmvVIp9fP/view?usp=share_link

Take this zip file and extract the content into C:\PHP. If it ask you to trust the zip file, choose to keep anyway and continue onward, downloading VC_redist.x86.exe and MySQL. A note for SQL, make sure you follow these steps: Typical Setup ->
Launch Configuration Wizard (after install) ->
Standard Configuration ->
Password
<br />

<h2> Installation Setup: osTicket</h2>

<p>
<img src="https://github.com/Aranis324/osticket-prereqs/assets/163223660/18653918-3ce3-4601-89e8-62ae8d7fd334"/>
</p>
<p>
So, you have all the prereq files installed, we can *fianlly* get into installing osTicket. We'll start opening IIS as an admin (right click the application to do so) then go to PHP. You'll realize that it's not enabled, so to fix the probem, click where it says Register New PHP Version, and go to that C Drive we made earlier, choosing PHP CGI. Then go back to IIS, restart the server in order to refresh it.
<br />

<p>
<img src="https://github.com/Aranis324/osticket-prereqs/assets/163223660/1840123d-fc3c-4c2c-872e-ce5013324e51"/>
</p>
<p>
Now it's time to finally install osTicket. Download this zip file https://drive.google.com/open?id=1VeVXKlzHDRjeaVUL99ptq7qYbrbXdFxJ&usp=drive_copy and go to your computers files. It's a good idea to open up two pages so you can drop the required folder into the right place with minimal effort. 

Go to the new zip folder, extract and copy the upload folder. Then go to your C-Drive and find inetpub\wwwroot and paste that upload folder into this area. Once thats done, rename the upload file within wwwroot into osTicket
<br />


<p>
<img src="https://github.com/Aranis324/osticket-prereqs/assets/163223660/3e5a836f-38a1-4e5c-8024-e9874bcb8fb5"/>
</p>
<p>
Once osTicket is put into our files, just to make sure things go right, close out IIS and reopen it as an admin. On the left side will be some dropdowns that will take us to osTicket. Drop down Sites, Default Web Site, and click the osTicket folder, then on the right side click Browse, and voilla! osTicket will have successfully opened. We've won the battle, but not the war. 
<br />

<h2>osTicket</h2>

<p>
<img src="https://github.com/Aranis324/osticket-prereqs/assets/163223660/af89e762-9220-43b1-b9f8-f050bede3e33"/>
</p>
<p>
So, osTicket has finally opened, but you may realize some features aren't active. While they are optional, you can't utilize osTicket in its entirety like this tutorial intends. 
<p>
<img src="https://github.com/Aranis324/osticket-prereqs/assets/163223660/af3c19c7-2df9-4786-9655-1dd5d37f01f3"/>
</p>
<p>
To start fixing this issue, go to IIS and drop down sites -> Default -> osTicket, double click PHP Manager, click Enable or Disable an extension and enable the following: php_imap.dll, php_intl.dll, php_opcache.dll. The next step is simple, go to your C Drive and rename C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php to C:\inetpub\wwwroot\osTicket\include\ost-config.php. Once it's all enabled, refresh osTicket from your browser and see whats changed!
<br />
<p>
<img src="https://github.com/Aranis324/osticket-prereqs/assets/163223660/f6ae1f49-fe1e-40ee-80ad-235cc30a005a"/>
</p>
<p>
<img src="https://github.com/Aranis324/osticket-prereqs/assets/163223660/8260d80d-881a-4aa7-9cf8-50c8530cd360"/>
</p>
<p>
The last thing to do is going to be opening access to the ost-config file. Find it in your C Drive by going through inetpub -> wwwroot -> osTicket -> include, then find the file and right click it open the properties menu. From here you'll go through Security, click Advanced and then Disable Inheritance and Remove all Inherited Permissions on this Project. Once it's done, click Select a Principle, type "Everyone" into the chat box, click ok and check the box that says Full Control. After all that is done, go back to osTicket and continue putting in the necessary information.
<br />
<p>
<img src= "https://github.com/Aranis324/osticket-prereqs/assets/163223660/db06e08a-d38c-4883-8418-dedf734942e5"/>
</p>
<p>
<img src="https://github.com/Aranis324/osticket-prereqs/assets/163223660/a8f74edc-18d2-481e-8428-2e84b8de87f8"/>
</p>
<p>
The final step in our master plan is to install HeidiSQL in order to make a database for osTicket to use. Download HeidiSQL from here https://docs.google.com/document/d/1WovrX2DaS9xkfaSr4LXyB4YnnWpXIgPCMMbbfgHmGVw/edit

Once it's installed and open, use the sign in you made when you installed MySQL. Then when you've fully opened HeidiSQL, right click where it says Unamed and click New Database, naming it osTicket.
<br />
<p>
<img src="https://github.com/Aranis324/osticket-prereqs/assets/163223660/f166692b-81a9-45bc-b4fc-a6c751b35542"/>
</p>

And with all that, were finally done! Go ahead and type in all of the information into the database settings. 
<br />

<p>
<img src="https://github.com/Aranis324/osticket-prereqs/assets/163223660/5d36e2c9-8877-478c-aade-ae1caf9e9575"/>
</p>
osTicket should now be installed with no issues and you can continue with logging in. Use this URL to enter osTicket once everything is set up http://localhost/osTicket/

A little post installation cleanup you can do is delete the setup foldr of C:\inetpub\wwwroot\osTicket\setup, and set permissions for ost.config to where only the boxes "Read" and "Read and Execute" are checked on
<br />
