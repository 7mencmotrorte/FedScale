
 
Memory acquisition is the first step in memory analysis. Before any analysis canbe done, we need to acquire the memory in the first place. There are a number ofcommercial solutions to acquire memory, but sadly open source solutions havebeen abandoned or not maintained (For example win32dd has been a popularsolution many years ago but has now been commercialized and is no longer opensource).
 
**Download ✪ [https://zoohogonka.blogspot.com/?file=2A0SS1](https://zoohogonka.blogspot.com/?file=2A0SS1)**


 
We believe in open source forensic tools to make testing and transparencyeasier. We also believe that the availability of open source solutions spursfurther development in the field and enables choices.
 
That is the reason we feel an open source, well tested and capable forensicmemory acquisition tool is essential - we call it the Pmem suite of tools. Thepmem acquisition tool aims to provide a complete imaging solution for Windows,Linux and OSX.
 
As from Version 1.1, the winpmem drivers support writing to memory as well asreading. This capability is a great learning tool since many rootkit hidingtechniques can be emulated by writing to memory directly. For example thefollowing Rekall session illustrates changing the name of the binary:

Since this is a rather dangerous capability, the signed binary drivers havewrite support disabled. The unsigned binaries (really self signed with a testcertificate) can not load on a regular system due to them being test selfsigned. You can allow the unsigned drivers to be loaded on a test system byissuing (see -us/library/windows/hardware/ff553484(v=vs.85).aspx):
 
Due to the nature of physical memory access many things are very platformdependent. The tool is designed to work on 64 bit Intel Macs. It can probably becompiled to work in 32 bit mode, the binary distribution however only contains64 bit binaries.
 
There should be little argument that with today's threats you should always acquire a memory image when dealing with any type of malware. Modern desktops can have 16 gigabytes of RAM or more filled with evidence that is usually crutial to understanding what was happening on that machine. Failure to acquire that memory will make analyzing the other forensic artifacts difficult or in some cases impossible. Chad Tilbury (@chadtilbury) recently told me about a new memory acquisition tool that I want to share with the ISC readers. It is called winpmem. It is written by Michael Cohen. It is free and it is available for download here. Here is a look at it.
 
You can see there are two executables. They are named winpmem\_1.4.exe and winpmem\_write\_1.4.exe. I'll come back to winpmem\_write\_1.4.exe later. There is also a "binaries" directory that includes a couple of device drivers and a Python script. That sounds like fun! I'll come back to that one later as well. For now, lets talk about winpmem\_1.4.exe. If you run it without any parameters you will get a help screen. It looks like this:
 
This will create a raw memory image named "memory.dmp" suitable for analysis with Volatility, Mandiants Redline and others. The tool can also create a crash dump that is suitable for analysis with Microsoft WinDBG. To do so you just add the "-d" option to your command line like this:
 
Now, some of you may be thinking, "So what! I can already dump memory with dumpit.exe, Win32dd.exe, win64dd.exe and others." Well, you are right. But if you have malware that is looking for those tools, now you have another option. While winpmem might look like a mild mannered memory acquisition tool, it actually has super powers. The BEST part of winpmem (IMHO) is in those components that I conveniently glazed over. I'll take a look at winpmem\_write\_1.4.exe and, better yet, that Python script in my next journal entry.
 
Winpmem may appear to be a simple a memory acquisition tool, but it is really much more. In yesterday's diary I gave a brief introduction to the tool and showed how you can use it to create a raw memory image. If you didn't see that article check it out for the background needed for today's installment. You can read it here.
 
One of my favorite parts of Winpmem is that it has the ability to analyze live memory on a running computer. Rather than dumping the memory and analyzing it in two seperate steps you can search for memory on a running system. Of course this will affect other forensics artifacts so you only want to use this on backup copies of your evidence. But this is also useful outside of forensics. There are all kinds of useful ways to use this tool. Searching for memory is useful to security reasearchers. You can search memory for strings that are in common pieces of malware. Do software vendors tell you that they encrypt sensative data in memory? You can use this tool to see if that is really true. So how do you do it?
 
Once the driver is installed it will create a \\.\pmem device object that you can open with Python. You will notice that it also reports 3 memory ranges. These are the ranges of physical memory addreses where the operating system stores data. In this case the first memory range starts at 0x1000 and has a length of 0x9e000. So it ends at memory address 0x9f000. The second range starts at 0x100000 and has a length of 0x3fdf0000. This leaves a conspicuous gap between the ranges. These gaps are used by the processor and other chipsets on your computer and aren't directly addressible by the Windows memory manager. Memory acquisition tools will only dump those ranges of memory used by the OS. This could lead to some interesting research where malware hides in those memory blind spots. Winpmem also has the ability to read those reserved areas of memory but doing so may lock up your machine.
 
To read memory it will require a little bit of Python code, but winpmem does the hard part for you. You can read memory with only 4 lines of Python code. All we have to do is import winpmem, create a handle to a file with win32file.CreateFile (the "fd" variable in the program below). Then use win32file.SetFilePointer() to point to the address you want to read. Finally call win32file.ReadFile() to read the bytes at that memory location. Thats it! So I threw together a quick script to allow me to search memory. I called this script "memsearch.py" when I saved it to my computer.
 
After writing the program I run python with the "-i" option so that I am dropped into an interactive shell with the new modules and variables already defined. I'll get an interactive Python prompt that I can use to call the memsrch() and readmem() functions. Because it is in a shell I can run multiple searches with different options until I find what I am looking for. Here is a short example calling each function once, In this case I read 100 bytes of memory starting at 18352196. Then I search for 5 occurences of the word "password" beginning at the address 0x100000.
 
readmem() is used to read data from memory. The readmem() function takes 3 parameters. The first is fd. This is the file handle that points to the \\.\pmem device created by the winpmem device driver. The 2nd parameter is the address to start reading from and the 3rd parameter is how much data to read.
 
memsrch() can be used to search memory for the string you specify. The memsrch() function takes several options. The first is again fd. The 2nd parameter is the search tearm to find in memory. The 3rd parameter is the starting address to being searching and the 4th parameter is the ending address. The rest of the parameters are optional. The 5th parameter is the number of matches to find in memory. The 6th parameter is used to turn on Verbose searching. If verbose is true the matching strings are printed to the screen. The last argument is the "includepython" argument. If includepython is set to True then it will allow the Python script to find itself as it searches through memory for matches.
 
Keep in mind that you are searching Physical memory. This is much different that virtual OS memory. Things may move around and you may find things in places where you do not expect them. To get a better understanding of how memory is being used by the OS read this excellent paper that accompanies the tool.
 
Sometimes, after a system has been compromised or hacked, it's important to extract forensically-relevant information. Random Access Memory (RAM) is considered volatile - meaning that it doesn't live long. Each time a computer is restarted, it flushes its memory from RAM. That means that, if a computer is hacked or compromised and is restarted, you'll lose a lot of information that tells the story about how the system was compromised.
 
In this blog, I'll be going over how to capture Windows memory using winpmem and how to analyze it with Volatility. I set up a virtual Windows machine for a CTF I ran back in 2018 called Guardians CTF; you'll see some references to it as I walk through my analysis. I simulated an attack where I, as the attacker, uploaded netcat as a listener. Nothing too fancy, I just wanted to showcase how to distinguish legitimate and illegitimate processes. Then, using Volatility on Kali, I'll walk through how to analyze the raw memory dump.
 
The --output mem.raw option was used to name the output as memdump.raw. The --format raw and --volume\_format raw options were used to output the memory in raw format (as opposed to something like aff4). After several minutes, the memory dump finished. I then transferred the raw memory file, memdump.raw, to my Kali machine.
 
Now that my raw memory file was on my Kali machine, was ready to use Volatility. This tool comes packaged with Kali, but if you're using a machine that does not already have Volatility installed, you can install it on using a package manager. If you use apt like I do, you can run this command on a Linux machine to install Volatility:
 
This part frustrates a lot of analysts. You can typically only analyze memory d