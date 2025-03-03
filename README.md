<p align="center">
<img src=https://github.com/user-attachments/assets/1e9245e8-ffcf-4492-bf14-38f3c738a874 />
</p>

<h1>This lab will go over the steps required to setup a fresh install of osTicket, which is a free, open source ticketing system.</h1>
<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10 Pro (Version 22H2)

<h2>Deployment and Configuration Steps</h2>

First, download the required files for osTicket, which you can find here:
  - [osTicket](https://drive.usercontent.google.com/download?id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD&export=download)

<p align="center">
Extract the files onto the desktop for easy access. <br/>
<img src=https://github.com/user-attachments/assets/442ea3e4-1ba3-4806-96cf-8c866cdcb7ed />
</p>
<br/>
<br/>
  
Install and enable IIS with CGI. You can do so by following these steps:<br/> 
  - Open the Control Panel <br/>
  - Click 'Uninstall a Program' <br/>
  <img src=https://github.com/user-attachments/assets/3ed28a2f-0b32-4a29-abe0-818724d0a398 />
  
  - Click 'Turn Windows featires on or off' on the sidebar <br/>
  <img src=https://github.com/user-attachments/assets/034bd85f-d0d3-4fab-9f0b-ea1ae623adf6 />

  -  Scroll until you see Internet Information Services. Then, click on the box and open the folder, open 'World Wide Web Services', then 'Application Development Features', and finally click on the box for 'CGI', then hit OK. <br/>
  <img src=https://github.com/user-attachments/assets/0be47bbb-e21f-4d3e-886e-603932edec9d />
<br/>
<br/>

<p align="center">
Once installed, open the osTicket Installation File that you extracted, and install 'PHPManagerforIIS'. <br/>
<img src=https://github.com/user-attachments/assets/88a81bb9-ac38-4a73-8f65-15f0b9fd39ee />
<br/>
<br/>
Next, 'install rewrite_amd64_en-US'. <br/>
<img src=https://github.com/user-attachments/assets/3125c9e7-65eb-4eb0-a87a-c54c11d5c835 />
<br/>
<br/>
Create a new Directory in the C: Drive named 'PHP' <br/>
<img src=https://github.com/user-attachments/assets/150847a5-1219-4506-849d-37973d9d2b29 />
<br/>
<br/>
Install 'VC_redist.x86' <br/>
<img src=https://github.com/user-attachments/assets/74e166ec-f36e-4ff9-a4bd-14bcc8775496 />
<br/>
<br/>
From the osTicket folder, unzip the 'php-7.3.8-nts-Win32-VC15-x86' folder into 'C:/PHP'. <br/>
<img src=https://github.com/user-attachments/assets/2a83b970-993a-4635-b487-671868c30e24 />
<br/>
<br/>
Install 'mysql-5.5.62-win32.msi', choosing the 'Typical' setup type. <br/>
<img src=https://github.com/user-attachments/assets/e64155f6-8d27-4310-9a01-474293cf6a2f />
<br/>
<br/>
Once installed, make sure to launch the Instance Configuration Wizard. <br/>
<img src=https://github.com/user-attachments/assets/8ecf2a87-de49-49ba-92b9-7d8da008425b />
<br/>
<br/>
Select Standard Configuration, and set a password for the root, then hit Execute. <br/>
<img src=https://github.com/user-attachments/assets/eb69d125-cea6-40fb-8c00-92cc1ca3ecfb />
<img src=https://github.com/user-attachments/assets/9900f087-29e7-4b77-94ff-3cc3ea5f90aa />
<br/>
<br/>
Open IIS as an Administrator once finished. <br/>
<img src=https://github.com/user-attachments/assets/471a64c0-5a86-4d69-9677-16e0dd929449 />
<br/>
<br/>
Double Click on 'PHP Manager', then click 'Register new PHP version' <br/>
<img src=https://github.com/user-attachments/assets/806cd12e-582c-4335-be7a-cc1c81f82d7f />
<br/>
<br/>
Select the path to the PHP version, which will be in C:/PHP/, and select 'php-cgi'. <br/>
<img src=https://github.com/user-attachments/assets/2a7f580b-9a80-4e48-a1f8-acc6c08c474e />
<br/>
<br/>
Restart the IIS server, which you can do from the main screen on the right sidebar. <br/>
<img src=https://github.com/user-attachments/assets/54055b81-a9ef-4562-b76b-aab3d14463d9 />
<br/>
<br/>
Back in the osTicket Install folder, extract 'osTicket-v1.15.8' anywhere. <br/>
<img src=https://github.com/user-attachments/assets/be6014f4-d516-46e8-b674-b424d9c685c6 />
<br/>
<br/>
Within the folder you extracted, copy the folder named 'upload' into 'C:/inetpub/wwwroot', then rename 'upload' to 'osTicket'. <br/>
<img src=https://github.com/user-attachments/assets/7033e888-a926-4197-9f54-1ab0eabc5e9c />
<br/>
<br/>
Restart the IIS once more, then on the left sidebar, open 'Sites', 'Default Web Site', then 'osTicket'. <br/>
<img src=https://github.com/user-attachments/assets/2170ce5b-411f-4668-b777-25423bdf34ec />
<br/>
<br/>
On the right sidebar, click on 'Browse *:80 (http) <br/>
<img src=https://github.com/user-attachments/assets/ce82c182-3dc6-464b-b52c-95f03747a2df />
<br/>
<br/>
It should show some recommended features being disabled. From here, reopen the IIS window, naviagte back to the osTicket folder in the IIS window, open the PHP Manager, and click 'enable or disable an extension'. <br/>
<img src=https://github.com/user-attachments/assets/a5e3feda-cb94-494f-936d-4f547ac8ecc5 />
<br/>
<br/>
Enable 'php_imap.dll', 'php_intl.dll', and 'php_opcache.dll', restart the IIS, then refresh the browser. <br/>
<img src=https://github.com/user-attachments/assets/14932fd0-1623-4954-b5e8-5d06a53beae9 />
<br/>
<br/>
Navigate to 'C:/inetpub/wwwroot/osTicket/include', then rename 'ost-sampleconfig.php' to 'ost-config.php' <br/>
<img src=https://github.com/user-attachments/assets/d3caddb8-72c5-4766-8a82-c7338a80001b />
Right-click on 'ost-config.php', open Properties, click on the 'Security' Tab, then click 'Advanced'. Disable inheritance, hit 'Remove all inherited permissions from this object', then add a new permission to Everyone and Click 'Full Control', then Apply. <br/>
<img src=https://github.com/user-attachments/assets/a06059c4-674e-43a7-95c2-6a79f2dd957c />
<br/>
<br/>
Go back to the browser and click Continue a the bottom of the window. <br/>
<img src=https://github.com/user-attachments/assets/1583fc28-38fc-4580-9cb6-3ddf0162aeb5 />
<br/>
<br/>
Fill in the boxes with the information you need to put in. At the bottom for Database Settings, for the MySQL Database, enter osTicket. Username can be anything you'd like, and Password will be the password you set whenever you installed 'mysql-5.5.62-win32.msi', then click install at the bottom of the screen. <br/>
<img src=https://github.com/user-attachments/assets/3610fddc-6e18-45a0-941c-49c77dc7a3e6 />
<br/>
<br/>
Back in the osTicket install folder, install 'HeidiSQL'. <br/>
<img src=https://github.com/user-attachments/assets/b7c6d71a-5da9-4178-90fc-b39d5331fa0e />
<br/>
<br/>
Open HeidiSQL once installed, open a New session, using the same username and password that you setup before during the osTicket setup in the broswer. If there isn;t a database named 'osTicket', make one now. <br/>
<img src=https://github.com/user-attachments/assets/ec15f4ab-c18f-4320-88c2-36c10f289fb3 />
<br/>
<br/>
Go back to the broswer, and click on the link to open the admin panel, and log in. If successful, this screen should open up. <br/>
<img src=https://github.com/user-attachments/assets/4cf6e824-7349-48a0-91ca-2e66945bc08a />
<br/>
<br/>
Finally, to clean up, head back to 'C:\inetpub\wwwroot\osTicket', delete the 'setup' folder, and change the permissions for C:\inetpub\wwwroot\osTicket\include\ost-config.php' to Read Only. Once done, you've successsfully setup osTicket!



























  



  



