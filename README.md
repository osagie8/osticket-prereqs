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
__Step 4__ - 

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
 ![alt text](/MyScreenshots/SCR-20241117-ukec.png) 
 ![alt text](/MyScreenshots/SCR-20241117-ukkr.png) 
 ![alt text](/MyScreenshots/SCR-20241117-ukoc.png) 
 ![alt text](/MyScreenshots/SCR-20241117-ukrv.png) 
 ![alt text](/MyScreenshots/SCR-20241117-uktz.png) 
 ![alt text](/MyScreenshots/SCR-20241117-ukvz.png) 
 ![alt text](/MyScreenshots/SCR-20241117-ulby.png) 
 ![alt text](/MyScreenshots/SCR-20241117-ulgd.png) 
 ![alt text](/MyScreenshots/SCR-20241117-uljw.png) 
 ![alt text](/MyScreenshots/SCR-20241117-ullv.png) 
 ![alt text](/MyScreenshots/SCR-20241117-ulpb.png) 
 ![alt text](/MyScreenshots/SCR-20241117-uluj.png) 
 ![alt text](/MyScreenshots/SCR-20241117-ulws.png) 
 ![alt text](/MyScreenshots/SCR-20241117-ulyd.png) 
 ![alt text](/MyScreenshots/SCR-20241117-ulzy.png) 
 ![alt text](/MyScreenshots/SCR-20241117-umex.png) 
 ![alt text](/MyScreenshots/SCR-20241117-umgn.png) 
 ![alt text](/MyScreenshots/SCR-20241117-umhz.png) 
 ![alt text](/MyScreenshots/SCR-20241117-umka.png) 
 ![alt text](/MyScreenshots/SCR-20241117-umqq.png) 
 ![alt text](/MyScreenshots/SCR-20241117-umup.png) 
 ![alt text](/MyScreenshots/SCR-20241117-umwg.png) 
 ![alt text](/MyScreenshots/SCR-20241117-unau.png) 
 ![alt text](/MyScreenshots/SCR-20241117-unyx.png) 
 ![alt text](/MyScreenshots/SCR-20241117-uocp.png) 
 ![alt text](/MyScreenshots/SCR-20241117-uoii.png) 
 ![alt text](/MyScreenshots/SCR-20241117-uouo.png) 
 ![alt text](/MyScreenshots/SCR-20241117-upga.png) 
 ![alt text](/MyScreenshots/SCR-20241117-upig.png) 
 ![alt text](/MyScreenshots/SCR-20241117-uplt.png) 
 ![alt text](/MyScreenshots/SCR-20241117-upqr.png) 
 ![alt text](/MyScreenshots/SCR-20241117-uqek.png) 
 ![alt text](/MyScreenshots/SCR-20241117-uqhb.png) 
 ![alt text](/MyScreenshots/SCR-20241117-uqlo.png) 
 ![alt text](/MyScreenshots/SCR-20241117-uqom.png) 
 ![alt text](/MyScreenshots/SCR-20241117-uqtd.png) 
 ![alt text](/MyScreenshots/SCR-20241117-uqwk.png)
 ![alt text](/MyScreenshots/SCR-20241117-urgg.png)
 ![alt text](/MyScreenshots/SCR-20241118-bacz.png) 
 ![alt text](/MyScreenshots/SCR-20241118-bafy.png) 
 ![alt text](/MyScreenshots/SCR-20241118-bbmy.png) 
 ![alt text](/MyScreenshots/SCR-20241118-bbuw.png) 
 ![alt text](/MyScreenshots/SCR-20241118-bcah.png) 
 ![alt text](/MyScreenshots/SCR-20241118-bcel.png) 
 ![alt text](/MyScreenshots/SCR-20241118-bcta.png) 
 ![alt text](/MyScreenshots/SCR-20241118-bczw.png) 
 ![alt text](/MyScreenshots/SCR-20241118-bdhm.png) 
 ![alt text](/MyScreenshots/SCR-20241118-bdjr.png) 
 ![alt text](/MyScreenshots/SCR-20241118-bdom.png) 
 ![alt text](/MyScreenshots/SCR-20241118-bgvo.png) 
 ![alt text](/MyScreenshots/SCR-20241118-bhiw.png) 
 ![alt text](/MyScreenshots/SCR-20241118-bhqb.png) 
 ![alt text](/MyScreenshots/SCR-20241118-bhti.png) 
 ![alt text](/MyScreenshots/SCR-20241118-biau.png) 
 ![alt text](/MyScreenshots/SCR-20241118-bihb.png) 
 ![alt text](/MyScreenshots/SCR-20241118-biru.png) 
 ![alt text](/MyScreenshots/SCR-20241118-biwi.png) 
 ![alt text](/MyScreenshots/SCR-20241118-bjdd.png) 
 ![alt text](/MyScreenshots/SCR-20241118-bjen.png) 
 ![alt text](/MyScreenshots/SCR-20241118-bjoo.png) 
 ![alt text](/MyScreenshots/SCR-20241118-bjqj.png) 
 ![alt text](/MyScreenshots/SCR-20241118-bkjg.png) 
 ![alt text](/MyScreenshots/SCR-20241118-bkop.png) 
 ![alt text](/MyScreenshots/SCR-20241118-bktf.png) 
 ![alt text](/MyScreenshots/SCR-20241118-bkws.png) 
 ![alt text](/MyScreenshots/SCR-20241118-blae.png) 
 ![alt text](/MyScreenshots/SCR-20241118-blfy.png) 
 ![alt text](/MyScreenshots/SCR-20241118-bliw.png) 
 ![alt text](/MyScreenshots/SCR-20241118-blon.png) 
 ![alt text](/MyScreenshots/SCR-20241118-blql.png) 
 ![alt text](/MyScreenshots/SCR-20241118-bltt.png) 
 ![alt text](/MyScreenshots/SCR-20241118-blzi.png) 
 ![alt text](/MyScreenshots/SCR-20241118-bmbz.png) 
 ![alt text](/MyScreenshots/SCR-20241118-bmqa.png) 
 ![alt text](/MyScreenshots/SCR-20241118-bnfn.png) 
 ![alt text](/MyScreenshots/SCR-20241118-bnhb.png) 
 ![alt text](/MyScreenshots/SCR-20241118-bnin.png) 
 ![alt text](/MyScreenshots/SCR-20241118-bnkz.png) 
 ![alt text](/MyScreenshots/SCR-20241118-bnnm.png) 
 ![alt text](/MyScreenshots/SCR-20241118-bnrh.png) 
 ![alt text](/MyScreenshots/SCR-20241118-bnur.png) 
 ![alt text](/MyScreenshots/SCR-20241118-bnyn.png) 
 ![alt text](/MyScreenshots/SCR-20241118-boav.png) 
 ![alt text](/MyScreenshots/SCR-20241118-bojd.png) 
 ![alt text](/MyScreenshots/SCR-20241118-bopk.png) 
 ![alt text](/MyScreenshots/SCR-20241118-bovk.png) 
 ![alt text](/MyScreenshots/SCR-20241118-bpcd.png) 
 ![alt text](/MyScreenshots/SCR-20241118-bpfv.png) 
 ![alt text](/MyScreenshots/SCR-20241118-bpml.png) 
 ![alt text](/MyScreenshots/SCR-20241118-bpqg.png) 
 ![alt text](/MyScreenshots/SCR-20241118-bqcc.png) 
 ![alt text](/MyScreenshots/SCR-20241118-bqpj.png) 
 ![alt text](/MyScreenshots/SCR-20241118-brdq.png) 
 ![alt text](/MyScreenshots/SCR-20241118-brie.png) 
 ![alt text](/MyScreenshots/SCR-20241118-bros.png) 
 ![alt text](/MyScreenshots/SCR-20241118-brxy.png)


