# osticket-rd-rd

<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />

-Windows Computer

-Google Chrome

<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Item 1
- Item 2
- Item 3
- Item 4
- Item 5




<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<strong>Part 1 (Create Virtual Machine in Azure) </strong>
  
<strong>Create a Resource Group </strong>
 - To create a Resource group, click the icon on  the Microsoft Azure homepage named Resource groups.
 - If you do not see this icon, you can simply type "Resource Groups" in the Microsoft Azure search box.
 - Look to the upper left side of the screen for a plus sign with the word Create next to it. Click it.
 - Do you see Resource group *? In the empty box next to it, type the name of what you want your resource group to be called. It can be named anything you want.
 - After you name it, look to the bottom of the screen for a box with the words "Review + create" written inside of it and click it.
 - Once you see a green box at the top of the screen that says, "Validation passed", click the box at the bottom of the screen that says "Create".
 - Congratulations! You have just created your resource group!
  
<strong>Create a Windows 10 Virtual Machine (VM) with 2-4 Virtual CPUs </strong> <br>
 - To create the virtual machine, click the words Microsoft Azure near to the top of the screen, which will take you to the homepage. There will be an icon that says "Virtual machines". Click it.
 - If you don't see it, or just want to use another way, type "Virtual Machines" in the search box and click the first option presented.
 - On the upper left hand side of the screen, click the plus sign with the word "Create" next to it. Select the first option in the drop down menu that comes. It should be titled "Azure virtual machine".
 - Boxes you have to fill out:
	- Resource group *: Click the arrow on the right side of the box and select the name of the resource group you created.
	- Virtual machine name*: name it whatever you want
   	- Image*: Click the arrow in the right side of the box and select the option that includes "Windows 10"
   	- Size*: Pick any of the options that says "2 vcpus" or "4 vcpus"
   	- Username*: name it whatever you want
   	- Password*: whatever you want
   	- Confirm password*: just retype the password you chose
   	- Near the bottom of the screen, check the box next to the sentence: "I confirm I have an eligible Windows 10/11 license with multi-tenant hosting rights." Then click the blue box at the bottom that says, "Review + create"
   	- Once you see a green box at the top of the screen that says, "Validation passed", click the box at the bottom of the screen that says "Create".
   	- Wait until you see the words "Your deployment is complete" on your screen or you recieve a notification on your screen (a pop up box in the upper right side of screen) that say "Deployment succeeded".
		- You can also click on the bell to see the notifications (to find it look at the Microsoft Azure search box, then slide your eyes to the right; it should be the second icon. You can also hover your mouse over it and see if it says Notification. If it does, click it.)

Name: Vm-osticket <br>
Username: labuser (for example/whatever you chose) <br>
Password: osTicketPassword1! (for example/whatever you chose) <br>

<em> Screenshot idea: Screenshot the whole page with an example </em>

</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<strong> Part 2 (Installation) </strong>
  This part is super simple. What it mainly consists of is clicking and downloading things. 


<strong> A - Open Installation File Folder in VM </strong>

1) Log in to VM

2) Open Microsoft Edge, open new tab and paste this link: https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6



<strong> B - Install / Enable IIS in Windows WITH
CGI and Common HTTP Features</strong>

Right click start menu and Select run > <br>
(add screenshot) <br>
Type control > <br>
(add screenshot) <br>
Programs > <br>
(add screenshot) <br>
Turn Windows on/off > <br>
(add screenshot) <br>
Check Internet Info Service > <br>
Expand World Wide Web Services > <br>
Expand App Dev Features > <br>
Check CGI > <br>
Expand Common HTTP Feat > <br>
Check all boxes > <br>
Ok <br>

<strong> C - From the Installation Files, download and install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi) </strong>

<strong> D - From the Installation Files, download and install the Rewrite Module (rewrite_amd64_en-US.msi) </strong>

<strong> E - Create the directory C:\PHP </strong>

General idea:
Change downloads to C:, and then put a folder titled PHP inside of it

Steps:
File Explorer> <br>
(add screenshot) <br>
Change Downloads to C: > <br>
(add screenshot) <br>
Right click white space + new + folder > <br>
(add screenshot) <br>
Title it PHP <br>
(add screenshot) <br>


<strong> F - From the Installation Files, download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and unzip the contents into C:\PHP<br>
!! ATTENTION !! <br>
If this appears, choose to “Keep” the file: (add screenshot) </strong> <br>

<strong> G - From the Installation Files, download and install VC_redist.x86.exe. </strong>

<strong> H - From the Installation Files, download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi) </strong>
Typical Setup -> <br>
Launch Configuration Wizard (after install) -> <br>
Standard Configuration -> <br>
Password1

<strong> I - Open IIS as an Admin and Register PHP </strong>

1) Type IIS (1), right click it (2), select  Admin (3)

(add screenshot) <br>
   
2) PHP manager > Register new PHP > Click three dots ... > This Pc > PHP > php.cgi > Ok <br>

(add screenshot) <br>

<strong> J - Reload IIS (Open IIS, Stop and Start the server) </strong>
(add screenshot) <br>

1) Just open vm-osticket (far left side)

2) Just click restart (far right side)

<strong> K - Install osTicket v1.15.8 <br>
Download osTicket from the Installation Files Folder <br>
Extract and copy “upload” folder to c:\inetpub\wwwroot <br>
Within c:\inetpub\wwwroot, Rename “upload” to “osTicket” <br> </strong>

<strong> L - Reload IIS (Open IIS, Stop and Start the server) </strong> <br>
(add screenshot)

<strong> M - Go to sites -> Default -> osTicket <br>
On the right, click “Browse *:80” </strong> <br>
(add screenshot)

<strong> N - Enable extensions <br>
Go back to IIS, sites -> Default -> osTicket <br>
Double-click PHP Manager <br>
Click “Enable or disable an extension”<br>
Enable: php_imap.dll <br>
Enable: php_intl.dll <br>
Enable: php_opcache.dll <br>
Refresh the osTicket site in your browse, observe the changes </strong>

<strong> O - Rename: ost-config.php
From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
To: C:\inetpub\wwwroot\osTicket\include\ost-config.php</strong>

<strong> P - Assign Permissions: ost-config.php</strong> <br>
1) Right click ost-config> <br>
2) Pizza (P-S-A: Properties - Security - Advanced)> <br>
3) Disable inheritance > <br>
4) Remove All > <br>
5) ADD > <br>
6) Select a principal > <br>
7) Type everyone + Click check names > <br>
8) Ok > <br>
9) Click Full Control box (all boxes should automatically become checked, if not: check them) > <br>
10) OK > Apply > OK > OK <br>

<strong> Q - Disable inheritance -> Remove All</strong> <br>
1) Right click + PSA


<strong> R - New Permissions -> Everyone -> All</strong>
1) Add> <br>
2) Select a principal> <br>
3) Type everyone> <br>
4) Check names + check Full control (make sure all boxes checked) <br>

<strong> S - Continue Setting up osTicket in the browser (click Continue) </strong>

Name Helpdesk

Default email (receives email from customers)

What I used: <br>
Help desk name: Jay HelpDesk <br>
Default email: jay@helper.com <br>
First name: Jay <br>
Last name: Jackson <br>
Email: jay@gmail.com <br>
username: jay <br>
password: Password1 <br>

T - From the Installation Files, download and install HeidiSQL. <br>
Open Heidi SQL <br>
Create a new session, root/Password1 <br>
Connect to the session <br>
Create a database called “osTicket” 

U - Continue Setting up osticket in the browser
MySQL Database: osTicket <br>
MySQL Username: root <br>
MySQL Password: Password1 <br>
Click “Install Now!”

Congratulations, hopefully it is installed with no errors!
Browse to your help desk login page: http://localhost/osTicket/scp/login.php

End Users osTicket URL:
http://localhost/osTicket/ 

<strong> Clean up </strong><br>
1) Delete: C:\inetpub\wwwroot\osTicket\setup


<strong>Set Permissions to “Read” only: C:\inetpub\wwwroot\osTicket\include\ost-config.php </strong>
1) PSA (Properties, Security, Advanced)> <br>
2) Click everyone> <br>
3) Click Edit > <br>
4) Uncheck modify&write (only boxes with the word read in it should be checked - ex: read & execute, read)

Notes:
Browse to your help desk login page: http://localhost/osTicket/scp/login.php  
End Users osTicket URL: http://localhost/osTicket/ 

</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
