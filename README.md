<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

# osTicket - Prerequisites and Installation
This outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.

## Environments and Technologies Used

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

## Operating Systems Used #

- Windows 10 (21H2)

## Overview of Steps
__Step 1__ - Setting up our VM  
__Step 2__ - Connecting to our VM  
__Step 3__ - Installing osTicket Dependency Files  
__Step 4__ - osTicket Final

## Installation Steps

## Setting up our VM

- Navigate to the Azure Portal and go to Virtual Machines.

 ![alt text](/MyScreenshots/SCR-20241117-ucnx.png)

 
- Create a Virtual Machine
 ![alt text](/MyScreenshots/SCR-20241117-ucti.png)

-  Create a new resource group above the virtual machine. Mine is called osTicket.
 ![alt text](/MyScreenshots/SCR-20241117-udck.png) 

- Heres how I configured my Virtual Machine
    - Virtual machine name is osTicket-vm
    - Region used is West US 2.(Use what works for you)
    - Image: Windows 10 Pro
 - Then I made a user name and password for my VM.
 - After this is done, selet Review + Create
 ![alt text](/MyScreenshots/SCR-20241117-udtc.png)

 -  This should deploy the Virtual Machine so we can can connect to it.
 ![alt text](/MyScreenshots/SCR-20241117-uepy.png)
  ## Connecting to our VM
- Nagivate back to the Azure Portal > Virual Machines
- Copy the Public IP address of the Windows Virtual Machine that was just made. Mine is 74.179.80.249
 ![alt text](/MyScreenshots/SCR-20241117-uest.png)
- Open the Windows Remote App
- Select the "+" on the top right corner
 ![alt text](/MyScreenshots/SCR-20241117-uezh.png)
 - Select Add PC
 ![alt text](/MyScreenshots/SCR-20241117-ufci.png)
 - Paste the IP address from the Virtual machine that was created.
 - This virtual machine will be called osTicketVM
 ![alt text](/MyScreenshots/SCR-20241117-ufmg.png)
 - Select the osTicketVM and enter the credentials for the Virtual Machine. 
 ![alt text](/MyScreenshots/SCR-20241117-ufrz.png)
 - The Windows Remote App will grant access. 
 ![alt text](/MyScreenshots/SCR-20241117-ufuy.png) 

 ## Installing osTicket Dependency Files
 - Open the folder and extract all files to the Desktop
 ![alt text](/MyScreenshots/SCR-20241117-ugti.png)
 
 ![alt text](/MyScreenshots/SCR-20241117-uhih.png)
 - The zip folder should have 7 files located inside.
	- These are going to be all of the files we are going to use to install osTicket to our Virtual machine. 
 ![alt text](/MyScreenshots/SCR-20241117-uhml.png) 
 - osTicket runs on a webserver. So we have to enable our web server for use.
 - First, go to the control panel
 ![alt text](/MyScreenshots/SCR-20241117-uhuh.png)
 - Then nagivate to Programs > Uninstall a Program
 ![alt text](/MyScreenshots/SCR-20241117-uiao.png)
 - Select Turn Windows features on or off on the left hand side.
 ![alt text](/MyScreenshots/SCR-20241117-uild.png) 
 - Next we want to download Internet Information Services and CGI.
 - Internet Information Services > Application Development Features > CGI
 ![alt text](/MyScreenshots/SCR-20241117-ujcb.png) 
 - Press OK and let the changes be applied.
 ![alt text](/MyScreenshots/SCR-20241117-ujhs.png)
 - After the changes have been appllied we can test to see if IIS is working properly.
 - IIS uses 127.0.0.1 since its a localhost.
 - Below is what 127.0.0.1 looks before downlaoding IIS with CGI. 
 ![alt text](/MyScreenshots/SCR-20241117-ujmh.png) 
 - This is how it look s like when IIS is succesfully installed.
 ![alt text](/MyScreenshots/SCR-20241117-ujqy.png)
 - Next lets downlaod PHPManagerforIIS
 ![alt text](/MyScreenshots/SCR-20241117-ukec.png)
 - Go through installation 
 ![alt text](/MyScreenshots/SCR-20241117-ukkr.png)
 - Finish installation 
 ![alt text](/MyScreenshots/SCR-20241117-ukoc.png)
 - Lets install rewrite_amd64_en next 
 ![alt text](/MyScreenshots/SCR-20241117-ukrv.png)
 - Go through installation 
 ![alt text](/MyScreenshots/SCR-20241117-uktz.png)
 - Finish installation 
 ![alt text](/MyScreenshots/SCR-20241117-ukvz.png)
 - Open the C: drive in file explorer and create a folder called "PHP" 
 ![alt text](/MyScreenshots/SCR-20241117-ulby.png)
 - The C: drive should look like this when folder is created. 
 ![alt text](/MyScreenshots/SCR-20241117-ulgd.png) 
 - Now lets go back to our osTicket Install files and lets extract php-7.3.8
 ![alt text](/MyScreenshots/SCR-20241117-uljw.png) 
 - Select Browse
 ![alt text](/MyScreenshots/SCR-20241117-ullv.png)
 - Nviagte to the C: directory and select the PHP folder that was previously made. Then click on Select Folder. 
 ![alt text](/MyScreenshots/SCR-20241117-ulpb.png) 
 - Should look like this before extracting. Then select Extract.
 ![alt text](/MyScreenshots/SCR-20241117-uluj.png) 
 - Next lets install VC_redist
 ![alt text](/MyScreenshots/SCR-20241117-ulws.png)
 - Go through installation 
 ![alt text](/MyScreenshots/SCR-20241117-ulyd.png)
 - Finish Installation 
 ![alt text](/MyScreenshots/SCR-20241117-ulzy.png)
 - Lets install mysql-5.5.62 
 ![alt text](/MyScreenshots/SCR-20241117-umex.png)
 - Go through installation 
 ![alt text](/MyScreenshots/SCR-20241117-umgn.png)
 - Select __Typical__. 
 ![alt text](/MyScreenshots/SCR-20241117-umhz.png)
 - Select install 
 ![alt text](/MyScreenshots/SCR-20241117-umka.png)
 - Tick the lauch checkbox and select Finish. 
 ![alt text](/MyScreenshots/SCR-20241117-umqq.png)
 - Select Next 
 ![alt text](/MyScreenshots/SCR-20241117-umup.png)
 - Select __Standard Configuration__ 
 ![alt text](/MyScreenshots/SCR-20241117-umwg.png)
 - Leave as is. Install As Windows Service with check box ticked. 
 ![alt text](/MyScreenshots/SCR-20241117-unau.png) 
 - Modify Security settings
 	-Enter the username and password created earlier and select next.
 ![alt text](/MyScreenshots/SCR-20241117-unyx.png)
 - Select Execute 
 ![alt text](/MyScreenshots/SCR-20241117-uocp.png) 
 - Select Finish
 ![alt text](/MyScreenshots/SCR-20241117-uoii.png)
 - Now that php manager is installed, Open IIS Services
 ![alt text](/MyScreenshots/SCR-20241117-uouo.png)
 - Nagivate to PHP manager. 
 ![alt text](/MyScreenshots/SCR-20241117-upga.png) 
 - Select __Register new PHP version__.
 ![alt text](/MyScreenshots/SCR-20241117-upig.png)
 - Select Browse or the ... 
 ![alt text](/MyScreenshots/SCR-20241117-uplt.png) 
 - Go to the C: drive and nagivateto PHP > php-cgi > Open
 ![alt text](/MyScreenshots/SCR-20241117-upqr.png) 
 - 
 ![alt text](/MyScreenshots/SCR-20241117-uqek.png) 
 ![alt text](/MyScreenshots/SCR-20241117-uqhb.png) 
 - Select OK.
 ![alt text](/MyScreenshots/SCR-20241117-uqlo.png) 
 - Then Nagivate to the osTicket connection to restart the server.
 ![alt text](/MyScreenshots/SCR-20241117-uqom.png) 
 - First we select stop and then we press start.
 ![alt text](/MyScreenshots/SCR-20241117-uqtd.png) 
 ![alt text](/MyScreenshots/SCR-20241117-uqwk.png)
 - The IIS server has been restarted.
 - Now lets finally install osTicket.
 - Nagivate to osTicket Install files and extract filles to desktop
 ![alt text](/MyScreenshots/SCR-20241117-urgg.png)
 ![alt text](/MyScreenshots/SCR-20241118-bacz.png) 
 ![alt text](/MyScreenshots/SCR-20241118-bafy.png)
 - Open osTicket folder 
 ![alt text](/MyScreenshots/SCR-20241118-bbmy.png)
 - Select inetpub > wwwroot 
 ![alt text](/MyScreenshots/SCR-20241118-bbuw.png) 
 ![alt text](/MyScreenshots/SCR-20241118-bcah.png)
 - Then copy the __Upload__ folder from the osTicket File into the __wwwroot__ folder. 
 ![alt text](/MyScreenshots/SCR-20241118-bcel.png) 
 ![alt text](/MyScreenshots/SCR-20241118-bcta.png) 
 - Then change the name to "__osTicket__".
 ![alt text](/MyScreenshots/SCR-20241118-bczw.png) 
 - Restart the webserver again. Stop first
 ![alt text](/MyScreenshots/SCR-20241118-bdhm.png)
 - Start the server back up 
 ![alt text](/MyScreenshots/SCR-20241118-bdjr.png) 
 - Nagivate to osTicket-vm > Sites > Default Web Site.
 - Then select Browse *80
 ![alt text](/MyScreenshots/SCR-20241118-bdom.png)
 - The osTicket Installer should appear on your browser.
 - Now lets enable some extensions 
 ![alt text](/MyScreenshots/SCR-20241118-bgvo.png)
 - Select PHP Manager
 ![alt text](/MyScreenshots/SCR-20241118-bhqb.png)
 - Select enable or disable an extension. 
 ![alt text](/MyScreenshots/SCR-20241118-bhti.png)
 - From the list right click and enable __php_imap.dll__,__php_intl.dll__, and __php_opcache.dll__. 
 ![alt text](/MyScreenshots/SCR-20241118-biau.png) 
 ![alt text](/MyScreenshots/SCR-20241118-bihb.png) 
 ![alt text](/MyScreenshots/SCR-20241118-biru.png)
 - This is how it should look like with those three enabled. 
 ![alt text](/MyScreenshots/SCR-20241118-biwi.png) 
 - The osTicket Installer page should update  with more green checks
 ![alt text](/MyScreenshots/SCR-20241118-bjdd.png) 
 ![alt text](/MyScreenshots/SCR-20241118-bjen.png) 
 - Navigate to osTicket > include and highlight ost-sampleconfig.php.
 ![alt text](/MyScreenshots/SCR-20241118-bjoo.png)
 ![alt text](/MyScreenshots/SCR-20241118-bjqj.png)
 - Change ost-sampleconfig.php to ost-config.php. 
 ![alt text](/MyScreenshots/SCR-20241118-bkjg.png) 
 - This is how it should look like
 ![alt text](/MyScreenshots/SCR-20241118-bkop.png) 
 - Right click and go to properties.
 ![alt text](/MyScreenshots/SCR-20241118-bktf.png) 
 - Then go to Security.
 ![alt text](/MyScreenshots/SCR-20241118-bkws.png) 
 - Select __Advanced__
 ![alt text](/MyScreenshots/SCR-20241118-blae.png) 
 - Select __Disable Inheritance__
 ![alt text](/MyScreenshots/SCR-20241118-blfy.png)
 - Select __Remove all inherited permissions from this object 
 ![alt text](/MyScreenshots/SCR-20241118-bliw.png)
 - Select Add 
 ![alt text](/MyScreenshots/SCR-20241118-blon.png) 
 - Select __Select a principal__
 ![alt text](/MyScreenshots/SCR-20241118-blql.png) 
 - Then type in "everyone" and click on __Check Names__ and then press OK.
 ![alt text](/MyScreenshots/SCR-20241118-bltt.png) 
 - Then check the __Full Control__ checkbox and Press OK.
 ![alt text](/MyScreenshots/SCR-20241118-blzi.png)
 - Then click on __Apply__ and __OK__. 
 ![alt text](/MyScreenshots/SCR-20241118-bmbz.png) 
 - Press OK.
 ![alt text](/MyScreenshots/SCR-20241118-bmqa.png)
 - Navigate back to the web browser to osTicket Installer and select Continue.
 - Enter credentials that will work for you.
   - Just make sure the email addresses are different.
 ![alt text](/MyScreenshots/SCR-20241118-bnfn.png) 
 - The SQL section is left blank. Lets install SQL 
 ![alt text](/MyScreenshots/SCR-20241118-bnin.png) 
 - Nagivate back to the ___osTicket Installation files__ and go to __HeidiSQL_12.30.6589_Setip__
 ![alt text](/MyScreenshots/SCR-20241118-bnkz.png) 
 - Go through installation
 ![alt text](/MyScreenshots/SCR-20241118-bnnm.png) 
 - Finish the installation. Make sure Launch HeidiSQL is checked.
 ![alt text](/MyScreenshots/SCR-20241118-bnrh.png) 
 - Once HeidiSQL loads, Select __Skip__.
 ![alt text](/MyScreenshots/SCR-20241118-bnur.png) 
 - Select __New__.
 ![alt text](/MyScreenshots/SCR-20241118-boav.png) 
 - Type in the creds that was made earlier when seeting up SQL and then Press OK.
 ![alt text](/MyScreenshots/SCR-20241118-bojd.png) 
 - __Unnamed__ will be created.
 ![alt text](/MyScreenshots/SCR-20241118-bopk.png) 
 - Right click __Unncamed__ > __Create new__ > __Database__.
 ![alt text](/MyScreenshots/SCR-20241118-bovk.png) 
 - Name the database "__osTicket__"
 ![alt text](/MyScreenshots/SCR-20241118-bpcd.png) 
 - __osTicket__ databse will be made in __Unnamed__
 ![alt text](/MyScreenshots/SCR-20241118-bpfv.png)
 - Then Nagivate back to the __osTicket Installer__ on the web browser.
 - Enter the credentials for the SQL Database and press __Install now!__
 ![alt text](/MyScreenshots/SCR-20241118-bpml.png) 
 - __osTicket__ will load!
 ![alt text](/MyScreenshots/SCR-20241118-bpqg.png) 
 - Notice how Heidi has been updated with various table in our osTicket database.
 ![alt text](/MyScreenshots/SCR-20241118-bqcc.png) 
 - osTicket is installed.
 ![alt text](/MyScreenshots/SCR-20241118-bqpj.png) 
 - Nagivate to the URL in the Address bar to access to Admin side of the Help Desk
 ![alt text](/MyScreenshots/SCR-20241118-brdq.png) 
 - Login to the Admin Help Desk.
 ![alt text](/MyScreenshots/SCR-20241118-brie.png) 
 - This is The Admin side of my Help Desk System
 ![alt text](/MyScreenshots/SCR-20241118-bros.png) 
 - Nagivate to the URL in the Address bar to access to user/client side of the Help Desk
 ![alt text](/MyScreenshots/SCR-20241118-brxy.png)
 - This is the client side of my Help Desk System

 ## osTicket has been succesfully installed


