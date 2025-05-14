# Cisco 7900 series

The provisioning process is the same whether your using SIP or SCCP frimware. You must be on the right frimware for the type of extenison you have. You can find a guide on how to install new frimware here.

If your phone already has stuff programmed to it, there is most of the time no need reset the phone. However, you will most likey need to remove the phones trust list. You will also need to delete the phones trust list if you installed the frimware via CUCM over DHCP.

Any phone running frimware load 9-4 or later will be able to be provisioned via HTTP which will work behind any router. However, phones on older firmware can only use TFTP. Some routers (mainly enterprise and higher end residential) work fine with TFTP. Most residential routers, however don't play nicely with TFTP. Xfinity and Spectrum's routers are examples. Some workarounds to this are to use a local TFTP server, to use our SBC server, or to port foward. You can find more details about TFTP here. If TFTP fails on SCCP frimware, the phone will failover to trying to register directly to our server without downloading the config files. The phone will work, but with reduced functionally and won't be able to download ringtones or wallpapers.

To provision the device:

1. Press the Settings button > Network Configuration > IPv4 Configuration
1. Set Alternate TFTP to Yes
1. Set TFTP Server 1 to 185.165.44.51
1. Validate and Save

The phone may reboot 

Go to "Security Configuration". Go down to Trust List and make sure the files are cleared. There may be files there if you got the phone used or got the frimware via CUCM.

Once thats done, go back to the main settings menu, select "Network Configuration", "IPv4 Setup", and go down to Alternate TFTP. Press \* \* #. The phone should confrim that settings are unlocked. If theres a password, you may need to install new frimware.

Set Alternate TFTP to Yes, and set the TFTP Server 1 to "185.165.44.51". Now click Save and close out the menu. If it worked, the phone now register. Depending on your phone and its frimware, it may restart to update the frimware.

If you have any issues, reach out to administration.