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

<h2>Installation Steps</h2>

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
After your done making the VM, we have to set up IIS for our VM. Open up a Remote Desktop Connection on your computer, then copy and paste the IP Address into there, and use the sign in you made for your VM. Then open up the control panel in your VM, and go to Programs, Turn On and Off Programs, then drop down Internet Inforamtion Services, World Wide Web Services, Application Development Features and check on CGI and Common HTTP Features. Then drop down Web Management Tools and check on ISS Managment Console. Now go back and double check if you have everything on before moving on to the next step
</p>
</p>
<br />

<p>
<img src="https://github.com/Aranis324/osticket-prereqs/assets/163223660/360ffbce-36a5-4249-af2b-76072c874394"/>
"/>

</p>
<p>
Once you have evertyhing above set up, we need to install software to help us run osTicket. Up in the prerequisites are all the instalation files requried for this process, of which our first batch of installation will be PHP Manager for IIS and the Rewrite Module. Noting fancy or specific to download these, so once thats done we can move on to the next step. in your C Drive, create a directory called C:\PHP and then download the following 
https://drive.google.com/file/d/1snNMtLdCOpMtkCyD4mvl9yOOmvVIp9fP/view?usp=share_link

Take this zip file and extract the content into C:\PHP. If it ask you to trust the zip file, choose to keep anyway and continue onward
<br />
