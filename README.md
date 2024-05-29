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
  
<strong>Create a Windows 10 Virtual Machine (VM) with 2-4 Virtual CPUs </strong> <br>

1) Type "portal.azure.com" in the url search bar, which should bring you to the Azure homepage and then click "Virtual Machines" (see screenshot)
![Screenshot 2024-05-19 120803](https://github.com/jaysixco/monitoring-traffic-rd/assets/160427311/3e38d2a9-6b4a-4191-8d7b-371ced1ae53d)

2) On the Virtual Machines page, click "+ Create" (in the left hand corner) and then click "Azure virtual machine" in the drop down menu (see screenshot)
![Screenshot 2024-05-19 121645](https://github.com/jaysixco/monitoring-traffic-rd/assets/160427311/1478bc17-d2e7-4b9e-9da5-d3f1a560becd)


4) For "Resource group *" - click "Create new" and then type whatever name you want <br>
   For "Virtual machine name *" - type whatever name you want <br>
   For "Region *" - Click any option that starts with ("US") <br>
   For "Availability Zone * - Leave it as "Zone 1"<br>
   For "Image *" - click "Windows 10 Pro, version 22H2 - x64 Gen2" <br>
   For "Size *" - Any option that has "2 vcpus" or "4 vcpus" <br>
   For "Username *" - whatever you want <br>
   For "Password *" - whatever you want <br>
   For "Confirm password *" - whatever you typed in previous step <br>
   For "Public inbound ports *" - "Allow selected ports" <br>
   For "Select inbound ports *" - "RDP (3389)" <br>
   Under "Licensing" check the box next to "I confirm I have an eligible Windows 10/11 license with multi-tenant hosting rights." <br>
   When you're done, cLick the blue button at the bottom that says "Review + create"
   An example of how the page should look like when done: <br>
   ![Full page 1](https://github.com/jaysixco/monitoring-traffic-rd/assets/160427311/24ba3f96-d158-43c7-a62b-2b8046d0ad02)
   ![Full page 2](https://github.com/jaysixco/monitoring-traffic-rd/assets/160427311/d0a69adc-1767-4477-824d-e83f8c83e24d)
   
6) Clicking "Review + create" from the previous step will bring you to this page. All you have to do is click the blue button that says "Create".
![Screenshot 2024-05-19 130702](https://github.com/jaysixco/monitoring-traffic-rd/assets/160427311/48b6672d-5ec0-46e2-b79e-4cdf45514bc8)

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

2) Open Microsoft Edge, open new tab and paste this link: https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6, which will bring you to this page that I will refer to from here on as the "Installation Files page": <br>
<img width="960" alt="Installation Files Page" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/a8a64155-d6a0-4bbc-bbe7-0da0be3f145a">



<strong> B - Install / Enable IIS in Windows WITH
CGI and Common HTTP Features</strong>

Right click start menu (1) and Select "Run" (2) > <br>
<img width="485" alt="Start - Run" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/11052743-ebe1-49f2-aad1-7973764c86df">
 <br>
Type control, then click "OK"> <br>
<img width="295" alt="control - ok" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/b4fcb9fa-a555-45bd-8dcf-39b5e527555e">
<br>
Click "Programs" > <br>
<img width="590" alt="Programs" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/7f9abe39-88a5-4e83-969e-eb8402f48a98">
<br>
Click "Turn Windows on/off" > <br>
<img width="590" alt="Windows on off" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/dc049e7b-4395-41ad-96d0-c3f383a8e872">
<br>
Check "Internet Information Service" (1), then click the small plus sign next to it to expand it (2) > <br>
<img width="347" alt="Internet Information Service" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/f22f6e37-369f-4c8e-a7b7-ca7303de2a71"> 
<br>
CLick small plus sign to Expand "World Wide Web Services" (1), Click small plus sign to Expand "Application Development Features" (2), then check box next to "CGI" (3) <br>
<img width="347" alt="Check CGI" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/3a9db1da-729b-423e-b01f-2f778bf4051e"> 
<br>
Scroll down a little bit and click small plus sign to Expand "Common HTTP Features", then make sure all the boxes are checked, then click "Ok". When done, Should look like this:
<img width="347" alt="Common HTTP Features" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/254933bb-3f0a-4adc-9aff-6d8a74ce8cff">
<br>

<strong> C - From the Installation Files page, download and install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi) </strong> <br>
1) Start at the Installation Files Page br>
<img width="960" alt="Installation Files Page" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/b6d5539d-ddfc-435d-809e-791d073f8ac3">
<br>
2) Click PHP Manager's download button <br>
<img width="960" alt="PHP - download button" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/9d7c8ae9-4d64-4dd3-9652-ada8132fbf3b">
<br>
3) If you see this popup, click "Download Anyway" <br>
<img width="422" alt="Click Downlo anyway" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/d58e7fa0-0ea2-4393-88d7-4b63fe822f07">
<br>
4) Should see this in the upper right hand corner. Click "Open File" <br>
<img width="276" alt="Click Open File" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/9ee52e6c-1eb1-45ef-9aed-a04577618c11">
<br>
5) On the Welcome page, click "Next"<br>
6) On the License Agreement page, click "I Agree" then click "Next" <br>
7) On the Installation Complete page, click "Close<br>
<br>

<strong> D - From the Installation Files page, download and install the Rewrite Module (rewrite_amd64_en-US.msi) </strong>
<br>
1) Start at the Installation Files Page br>
<img width="960" alt="Installation Files Page" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/b6d5539d-ddfc-435d-809e-791d073f8ac3">
<br>
2) Click the download button <br>
<img width="960" alt="rewrite download button" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/a2db8fbb-1104-447c-b9ff-99ce65e00260">
<br>
3) If you see this popup, click "Download Anyway" <br>
<img width="422" alt="rewrite - Click D anyway" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/8c6528e5-6623-4d0f-a01f-4b13231bb69b">
<br>
4) Should see this in the upper right hand corner. Click "Open File" <br>
<img width="275" alt="rewrite - open file" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/09a9bbc0-8470-4b09-b384-660042ebd1ec">
<br>
5) On the License Agreement Page, click the "I accept the terms in the LIcense Agreement" box, then click "Install" <br>
6) Then click the "Finish" button<br>
<br>

<strong> E - Create the directory C:\PHP </strong>

Steps: <br>
File Explorer> <br>
<img width="960" alt="file explorer" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/553498e5-4d5d-47cd-b446-6aa10879b0e1">
 <br>
Click "This PC" then click "C:" > <br>
<img width="590" alt="this pc - c" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/71f2e5fa-6d63-4994-993b-27bc1c54e4b3">
 <br>
Right click white space, hover mouse over "New", click "Folder" > <br>
<img width="590" alt="right click new folder" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/f7b83028-0a03-4131-a71c-6369199eac21">
<br>
Title it PHP <br>
<img width="590" alt="Title PHP" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/68605cd9-6036-43d9-a598-55e81586de34">
<br>


<strong> F - From the Installation Files, download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) and unzip the contents into C:\PHP<br>
1) Start at the Installation Files Page br>
<img width="960" alt="Installation Files Page" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/b6d5539d-ddfc-435d-809e-791d073f8ac3">
<br>
2) Click the PHP 7.3.8 download button <br>
<img width="958" alt="php 738 download button" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/66fe2096-93b2-4e4c-ac87-483399934b2e">
<br>
3a) !! ATTENTION !! <br>
If this appears, choose to “Keep” the file: (add screenshot) </strong> <br>
3b) If you see this popup, click "Download Anyway" <br>
<img width="420" alt="738 download anyway" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/1fc03d8c-cc37-4b72-a9b9-335de6c8fbd7">
<br>
4) Should see this in the upper right hand corner. Click "Open File" <br>
<img width="277" alt="php - open file" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/fe99b301-2737-4cea-becc-a7149bf50044">
<br>
5) Click File Explorer (1), click "Downloads (2), right click "php-7.3.8..." (3), click "extract All" (4) <br>
<img width="644" alt="click extract all" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/9c48071f-c146-4027-aa4d-74ff88469123">
<br>
6) click "Browse" <br>
<img width="441" alt="browse" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/0d3b791c-8af7-43ee-bdc6-65fb83bc64ef">
<br>
7) click "This pc", then click "C:" <br>
<img width="470" alt="this pc - c" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/e8f41dd1-21fc-40b8-a508-79a44ff4fe56">
 <br>
8) click "Select Folder" <br>
<img width="470" alt="select folder" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/b90dee1a-94cc-4eaa-8900-4546ccaf6552">
<br>
9) click "Extract" <br>
<img width="441" alt="browse" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/fc2135d2-d373-42ff-8b46-461785d4adea">
<br>


<strong> G - From the Installation Files, download and install VC_redist.x86.exe. </strong> <br>
1) Start at the Installation Files Page br>
<img width="960" alt="Installation Files Page" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/b6d5539d-ddfc-435d-809e-791d073f8ac3">
<br>
2) Click VC_redist's download button <br>
<img width="960" alt="vc - download button" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/5ad2afeb-3aa2-4e90-bb9b-a57b65b6a9b5">
 <br>
3) If you see this popup, click "Download Anyway" <br>
<img width="421" alt="vc - download anyway" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/4668bfb0-e290-428d-bbdb-0c01352dd6e7">
<br>
4) Should see this in the upper right hand corner. Click "Open File" <br>
<img width="274" alt="vc - open file" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/9fd1a690-44ed-4103-8370-86177f6c2269">
<br>
5) On this page that pops up, click the box next to "I agree to..." then click "Install" <br>
<img width="360" alt="vc - click I agree  then install" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/7a43f32c-df02-4deb-986b-78343541c6cf">
<br>
6) Click "Close" <br>
<img width="360" alt="vc - click close" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/9f8d26df-355c-421c-a4ae-d432f89c3866">
<br>

<strong> H - From the Installation Files, download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi) </strong> <br>
1) Start at the Installation Files Page br>
<img width="960" alt="Installation Files Page" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/b6d5539d-ddfc-435d-809e-791d073f8ac3">
<br>
2) Click MySQL 5.5.62's download button <br>
<img width="960" alt="mysq's - download button" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/20c3996f-f1bd-4062-9593-8fdcba7102c8">
<br>
3) If you see this popup, click "Download Anyway" <br>
<img width="420" alt="mysq - download anyway" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/2d05aef6-a1e8-4099-83da-7c666b7b4344">
<br>
4) Should see this in the upper right hand corner. Click "Open File" <br>
<img width="275" alt="mysq - open file" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/9da147fc-8738-4534-bd57-2924a8ed2b9d">
<br>
5) Welcome page, click "Next" <br>
<img width="386" alt="mysq - welcome page, click next" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/47981e67-8301-473a-bfd4-5b9e89b31193">
<br>
6) License Agreement page, click "I accept the terms..." (1), then click "Next" (2) <br>
<img width="386" alt="mysq - I accept the terms, next" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/cfeaa64e-bf0b-44a8-9041-458ca0f7725e">
<br>
7) Choose setup type page, click "Typical" <br>
<img width="386" alt="mysq - setup type, typical " src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/3c49f584-755d-4e1e-a841-e8f66af586d0">
<br>
8) Ready, click "Install" <br>
<img width="386" alt="ready, click Install" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/15f14e4b-6300-4056-aeb0-48843f7abcd1">
<br>
9) Completed. Click "Finish"
<img width="386" alt="Completed, click Finish" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/703deaf1-4f0e-4ad4-a503-0f226300cb43">
<br>
10) Instant Configuration page, click "Next"
<img width="374" alt="instance config, click next" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/cea6bebc-0f15-4302-9336-9f4cacef2799">
<br>
11) Click "Standard Configuation", then click "Next"
<img width="374" alt="standard, click next" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/325a05b7-bd6c-4543-baee-06e1305e4788">
<br>
12) Window Options page, click "Next"
<img width="374" alt="Window options, click next" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/6069643a-5d34-4018-8dae-3675b6bd6158">
<br>
13) Type a password, then click "Next"
<img width="374" alt="type password, click next" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/db02e606-9eee-41df-bdcf-88d399a610bb">
<br>
14) Ready to execute page, click "Execute"
<img width="374" alt="ready to eecute page, click execute" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/04b4dd5a-a2a0-42cd-89b6-bc8d4cfad443">
<br>
15) When that's done, press "Finish"
<img width="374" alt="When that's done, press finish" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/a490cc84-a903-49cb-af3a-fde517948a0a">
<br>

<strong> I - Open IIS as an Admin and Register PHP </strong>

1) Type IIS in start menu search box(1), click "Run as administrator" (2) <br>
<img width="588" alt="IIS, run as admin" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/044c166a-6400-41f9-b421-3719bd8eac99">
<br>  
2) Double click "PHP Manager" >
<img width="709" alt="double click PHP manager" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/94c4f761-1d7b-47fa-9d06-260f9d6599bb">
<br>
3) Click "Register new PHP" >
<img width="709" alt="click Register new PHP version" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/d19d2157-9025-48a5-99e0-a61a5433dbc5">
<br>
4) Click the three dots >
<img width="381" alt="click the three dots" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/e64bf95d-a016-425c-866f-8ebfff7ee377">
<br>
5) Scroll down, click "php.cgi", then click "Open">
<img width="470" alt="scroll down, click php-cgi, then click Open" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/3a123142-95e1-4567-b5cc-55cb5862f9b1">
<br>
6) Click "Ok" <br>
<img width="381" alt="click Ok" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/d2ba1fc0-b098-4a52-bc48-c4744caba754">
<br>

<strong> J - Reload IIS (Open IIS, Stop and Start the server) </strong> <br>
1) Press Back to get to IIS Manager page
<img width="709" alt="press back to get to main homepage" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/a0ad6313-a268-48d8-af1b-1035d6d3654c">
<br>
2) Click "Stop"
<img width="709" alt="click Stop" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/97f93bec-cf49-4e74-bddf-eb4a00e95e02">
<br>
3) Click "Start"
<img width="709" alt="click Start" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/3b90c9a2-f697-4695-a3ee-c46b26fcc6c1">
<Br>

<strong> K - Download and Install osTicket v1.15.8 from the Installation Files Folder </strong><br>
1) Start at the Installation Files Page br>
<img width="960" alt="Installation Files Page" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/b6d5539d-ddfc-435d-809e-791d073f8ac3">
<br>
2) Click osTicket's download button <br>
(add screenshot) <br>
3) If you see this popup, click "Download Anyway" <br>
(add screenshot)
<br>
4) Should see this in the upper right hand corner. Click "Open File" <br>
(add screenshot)
<br>
5) You should see this: (add screenshot) <br>
6) Right click File Explorer Icon (1), then click "File Explorer" (2) (add screenshot) <br>
7) Click "This Pc", scroll down, then double click "Windows (C:)" (add screenshot) <br>
8) Double click "inetpub" (add screenshot) <br>
9) Double click "wwwroot" (add screenshot) <br>
10) Open the "osTicket" folder next to the "wwwroot" folder so they're side by side, like this: (add screenshot) <br>
11) Click "upload" and drag it over the "wwwroot" folder (add screenshot) <br>
12) In the "wwwroot" folder, right click "upload", then click "Rename" (add screenshot) <br>
13) Type "osTicket" then hit enter (add screenshot) <br>

Extract and copy “upload” folder to c:\inetpub\wwwroot <br>
Within c:\inetpub\wwwroot, Rename “upload” to “osTicket” <br> </strong>

<strong> L - Reload IIS (Open IIS, Stop and Start the server) </strong> <br>
1) Press Back to get to IIS Manager page
<img width="709" alt="press back to get to main homepage" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/a0ad6313-a268-48d8-af1b-1035d6d3654c">
<br>
2) Click "Stop"
<img width="709" alt="click Stop" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/97f93bec-cf49-4e74-bddf-eb4a00e95e02">
<br>
3) Click "Start"
<img width="709" alt="click Start" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/3b90c9a2-f697-4695-a3ee-c46b26fcc6c1">
<Br>

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
2) P-S-A: Properties - Security - Advanced)> <br>
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
1) Start at the Installation Files Page br>
<img width="960" alt="Installation Files Page" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/b6d5539d-ddfc-435d-809e-791d073f8ac3">
<br>
2) Click the download button <br>
(add screenshot) <br>
3) If you see this popup, click "Download Anyway" <br>
(add screenshot)
<br>
4) Should see this in the upper right hand corner. Click "Open File" <br>
(add screenshot)
<br>

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

<p>
<h2> Screenshots for Later, just in case </h2> <br>
For Install the Rewrite Modue: <br>
a) Rewrite License Agreement Page 
<img width="385" alt="rewrite - lic agrment page jic" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/dd0e4442-6e26-4b78-99df-c8aa5d0fba63"> <br>
b) Rewrite Finish button page 
<img width="386" alt="rewrite - finish button" src="https://github.com/jaysixco/osticket-rd-rd/assets/160427311/87200cee-0c04-44ad-b37e-8ff25299d019"> <br>


  
</p>
