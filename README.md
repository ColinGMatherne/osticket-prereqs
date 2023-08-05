<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

# osTicket - Prerequisites and Installation
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.

## Environments and Technologies Used
- [Microsoft Azure (Virtual Machine)](https://github.com/ColinGMatherne/Azure-VM)
- Remote Desktop Protocol

## Operating Systems Used
- Windows 10

## List of Prerequisites
- Internet connection
- mySQL
- HeidiSQL
- OSTicket
- PHP
- PHP Manager For IIS
- URL Rewrite IIS
- Microsoft Visual Redist

## Installation Steps
1. Go to the Control Panel->Programs->Turn Windows features on or off and turn on Internet Information Services and add CGI

![Control Panel Search](https://github.com/ColinGMatherne/osticket-prereqs/assets/132864551/8cd48f5a-ba46-41ba-bc10-6dc14f800c55)
#
![Control Panel](https://github.com/ColinGMatherne/osticket-prereqs/assets/132864551/8501cf3f-4196-480d-a20f-90d50509ba74)
#
![Programs](https://github.com/ColinGMatherne/osticket-prereqs/assets/132864551/1b97576a-5041-4fc4-9c0c-fc20d086d040)
#
![IIS](https://github.com/ColinGMatherne/osticket-prereqs/assets/132864551/850bf6c5-c9ba-465e-a539-906986b5f7b0)
#
![IIS 2](https://github.com/ColinGMatherne/osticket-prereqs/assets/132864551/d2535079-3baf-4818-bad7-7f27dff8a2b5)


2. Install PHP MySQL MariaDB and PHP Manager 2 for IIS from the OSTicket [docs page](https://docs.osticket.com/en/latest/Getting%20Started/Installation.html) and also install HeidiSQL Microsoft Visual Redist and URL Rewrite IIS
   - Extract the PHP zip file to C:\PHP

![Extract PHP](https://github.com/ColinGMatherne/osticket-prereqs/assets/132864551/7f40a672-b831-43f4-bae0-2c8a96db746e)
#
![Extract to C PHP](https://github.com/ColinGMatherne/osticket-prereqs/assets/132864551/c2820c12-406f-4a8a-a0d6-c31b74f5aa81)

  - Install the other files leaving everything default
#
3. Extract OSTicket\upload to C:\inetpub\wwwroot and rename the folder to "osTicket"
![Upload rename](https://github.com/ColinGMatherne/osticket-prereqs/assets/132864551/076fb207-d9e7-4450-877d-9d9a626d9a83)

4. Go to IIS->PHP Manager and register the PHP CGI

![CGI Register](https://github.com/ColinGMatherne/osticket-prereqs/assets/132864551/1c4f621b-d170-4860-86b0-f883e1fcebc3)
#
![php-cgi exe](https://github.com/ColinGMatherne/osticket-prereqs/assets/132864551/ecaa68a9-20a7-4cda-a0c2-556c64624c6b)

5. Go to IIS Manager->Sites->Default Web Site->osTicket->PHP Manager and enable php_opcache, php_imap and php_intl from the disable section

6. Go to C:\inetpub\wwwroot\osTicket\include and rename ost-sampleconfig.php to ost-config.php then change to global write

![OSTicket](https://github.com/ColinGMatherne/osticket-prereqs/assets/132864551/05f62f5c-9c63-4fab-845a-27a098a77e69)
#
![ost properties](https://github.com/ColinGMatherne/osticket-prereqs/assets/132864551/58fb4c66-5ce6-4c2b-ab99-51d806078fb7)
#
![ost advanced 1](https://github.com/ColinGMatherne/osticket-prereqs/assets/132864551/c7d0912b-0498-4596-a57f-54453ed7a57c)
#
![ost di](https://github.com/ColinGMatherne/osticket-prereqs/assets/132864551/3b11b1eb-7805-4199-afe7-e689fc064e41)
#
![ost everyone](https://github.com/ColinGMatherne/osticket-prereqs/assets/132864551/e8d7cdf0-8954-4b36-910e-81f17c19375c)
#
![ost everyone fc](https://github.com/ColinGMatherne/osticket-prereqs/assets/132864551/21ec16ce-a960-4c08-9247-1ef306025028)

7. Go to HeidiSQL and create a new db

![Heidi 1](https://github.com/ColinGMatherne/osticket-prereqs/assets/132864551/3f4d386a-6df7-4a03-8892-c53e9a6a97c1)
  - In this area fill in the same information as you did setting up mariadb

#
![Heidi 2](https://github.com/ColinGMatherne/osticket-prereqs/assets/132864551/7052c7fb-d970-4e26-8416-887862bcd475)
#
![Heidi 3](https://github.com/ColinGMatherne/osticket-prereqs/assets/132864551/2736d0c6-9623-4b65-93a1-696b506a3e07)
#

8. Go back to osTicket in IIS Manager and click Browse http *:80
  - In this area just fill in the info and use the same info you just used again for the database section

![Heidi 4](https://github.com/ColinGMatherne/osticket-prereqs/assets/132864551/790e8b82-04bc-494f-acd8-47b724db32d2)

9. The final step is to go back to C:\inetpub\wwwroot\osTicket\include and change the permissions for ost-config.php to readonly and delete the setup folder in the parent directory


