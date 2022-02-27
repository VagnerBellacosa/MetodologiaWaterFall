# Thimbles & Care

Curtis Pew’s thoughts related to his job

- [Home](https://sites.utexas.edu/curtispe) - [About](https://sites.utexas.edu/curtispe/about/) - [The story of webAgent: webAgent 1](https://sites.utexas.edu/curtispe/the-story-of-webagent1/) - [A good idea revisited](https://sites.utexas.edu/curtispe/a-good-idea-revisited/)
- [Old mainframe hardware](https://sites.utexas.edu/curtispe/old-mainframe-hardware/) - [The story of webAgent: webAgent 2](https://sites.utexas.edu/curtispe/the-story-of-webagent-webagent-2/) - [Was webAgent a good idea?](https://sites.utexas.edu/curtispe/was-webagent-a-good-idea/)

## Old mainframe hardware

My major project right now is getting ready to migrate from our old tape libraries to a new virtual tape library. Going through my hardware folders on my Mac, I found a page I’d originally created on WebSpace (!) with photos of old mainframe hardware. I was thinking of where would be a good place to put that now, and decided this blog was it. I’ll also add some photos of more recent (but now obsolete) equipment.

## Tapes

Let’s get the tapes out of the way first.

[![Hitachi Hitachi 7490/7390 tape drives](https://sites.utexas.edu/curtispe/files/2020/07/T7490-300x252.jpg)](https://sites.utexas.edu/curtispe/files/2020/07/T7490.jpg)

Hitachi 7490/7390 tape drives with auto-loaders.

These are the oldest tape drives I have pictures of. These are Hitachi 7490 and 7390 tape drives. The twelve drives on the left (the 7490s) were IBM 3490 compatible, while the two on the right (the 7390s) were IBM 3480 compatible. 3490-compatible drives could read cartridges written on 3480-compatible drives, but not vice-versa. By this time we mostly used 3490 cartridges, but occasionally needed to send tapes to other data centers that only had 3480-compatible drives.

On these drives, tapes were mostly hand-loaded, but if you knew which tapes a job was going to use in what order you could put them in loader racks (you can see some above the 7390 drives) and put the rack on the drive and set it to auto-load.

[![IBM 3494 Automatic Tape Library](https://sites.utexas.edu/curtispe/files/2020/07/L3494-300x261.jpg)](https://sites.utexas.edu/curtispe/files/2020/07/L3494.jpg)

IBM 3494 Automatic Tape Library

This was our next tape system. The frames you see here had drives and racks for cartridges on the inside. Going down the middle was a track that a robot ran on. When a tape mount was requested, the robot would roll along the track to where the desired cartridge was, and a little arm would come out and grab the cartridge. Then the robot would roll to the drive and insert the cartridge. This library was donated to the University used by an oil company in Houston that had replaced it with a newer model. The drives and cartridges were IBM model 3590.

[![IBM TS3500 ATL](https://sites.utexas.edu/curtispe/files/2020/07/TS3500-280x300.jpg)](https://sites.utexas.edu/curtispe/files/2020/07/TS3500.jpg)

IBM TS3500 Automatic Tape Library

In April 2008 we replaced the 3494 ATL with two IBM TS3500 ATLs. One was placed in the primary data center, and the other in a backup data center. Most important data was written twice, one copy in each library. That way if a disaster took out one data center we’d have a copy in the other. These libraries had a rail and robot like the 3493, but since the 3592 drives and cartridges in it were smaller and held more data than the 3590 ones, each library only had two frames. The one on the left contained the drives and some cartridge racks, while the one on the right only contained racks. The cylindrical thing on the left is the input port where cartridges were inserted into the library. The blue thing to its left is a control panel.

[![Stand-alone tape drives](https://sites.utexas.edu/curtispe/files/2020/07/stand_alone_tape-116x300.jpg)](https://sites.utexas.edu/curtispe/files/2020/07/stand_alone_tape-scaled.jpg)

Stand-alone 3590 and 3592 tape drives

For receiving tapes from and sending tapes to other data centers, we had “stand-alone” drives outside the libraries, two 3590 drives and two 3592 drives. These drives, when used, were loaded manually. In this rack, the bottom device (behind the mesh) is the controller for the 3590 drives. The 3590 drives themselves are just above, labelled 640 and 641. Above them, the IBM System p5 serves as the controller for the 3592 drives, which are at the top right with their displays reading “EMPTY.” The cartridges sitting on the drives are cleaning cartridges.

The tape libraries will be replaced by a Dell/EMC DLm8500 in August 2020. There will be no replacement for the stand-alone tape drives; we use the internet instead of physical tape to send and receive data now.

## Printers

[![Xerox printers](https://sites.utexas.edu/curtispe/files/2020/07/Xprt-300x245.jpg)](https://sites.utexas.edu/curtispe/files/2020/07/Xprt.jpg)

Mainframe-attached Xerox laser printers

We used to have several large, high-speed Xerox printers directly attached to the mainframe on which mainframe job output was printed. The unit in the front of this picture was the operator console and controller, while the actual printing was done in the larger unit to the rear. The University started using printers like this in 1980 or 1981. In August 2006 these printers were retired in favor of internet protocol printers managed by central duplicating (now Document Solutions.)

They went away before I had access to digital photography, but up until nearly 2000 the University also had [IBM 1403](https://en.wikipedia.org/wiki/IBM_1403) “impact” or line printers.

## Communications

[![Communications controllers](https://sites.utexas.edu/curtispe/files/2020/07/comm-288x300.jpg)](https://sites.utexas.edu/curtispe/files/2020/07/comm.jpg)

IBM 3745 and 3172 communication control units

The device on the left is an IBM 3745 communications front-end processor. It was used to connect (via a token-ring network) to terminal control units all over campus; those control units were coaxially connected to 3270 terminals. Those communications used IBM’s SNA networking architecture. The 3745 also communicated with similar communications controllers connected to IBM mainframes in other data centers. (I know that we had a connection to the Texas Comptroller’s office’s mainframe this way, and I think there were banks at some point too.) Internet protocol communications eventually replaced all the uses for the 3745.

The 3172 controllers were used for non-SNA “locally-attached” 3270 terminals which were used as consoles. Starting with the z890, these were replaced by OSA-ICC features. The OSA features provide internet connectivity for IBM z mainframes. When configured with the Integrated Console Controller (ICC) function they emulate a 3172 to the z operating system and include a tn3270E server so workstation clients can be used as consoles.

## Processors and DASD

[![IBM z890 and ESS 800](https://sites.utexas.edu/curtispe/files/2020/07/z890-ESS-300x295.jpg)](https://sites.utexas.edu/curtispe/files/2020/07/z890-ESS.jpg)

IBM z890 processor and ESS 800 storage

The University purchased two IBM z890 eServer systems and two IBM Enterprise System Storage (ESS) “Shark” disk arrays at the end of 2004, and one of each was placed in production in January 2005. The second z890 and Shark were placed in the backup data center and the data in the primary Shark was mirrored to the secondary one. In case of a disaster the z890 in the backup center could be IPL’d using the mirrored disk to replace the primary z890. The picture is of the production z890 and Shark.

[![z10 BC I/O drawers](https://sites.utexas.edu/curtispe/files/2020/07/z10BC_io_front-300x225.jpeg)](https://sites.utexas.edu/curtispe/files/2020/07/z10BC_io_front-scaled.jpeg)

The front of the I/O drawers for the z10 BC

In March 2011 the production z890 was replaced with a z10 BC. I thought I had taken some pictures of the entire z10 BC, but if so I’ve misplaced them. This is a picture of the front of the two I/O drawers the z10 BC had, showing the FICON connections to disk and tape, the two cryptography features, and two of the network interface features.

Only the production z890 was replaced. We contracted with Sungard to provide DR services. We kept the backup z890 so it could dump the mirror disks to tape to be sent to Sungard in case of a disaster.

The z10 BC was replaced by the current IBM z14 ZR1 in August 2019.

[![Hitachi VSP electronics](https://sites.utexas.edu/curtispe/files/2020/07/VSP-225x300.jpg)](https://sites.utexas.edu/curtispe/files/2020/07/VSP-scaled.jpg)

Hitachi VSP controller and related electronics

At the same time we replaced the Sharks with Hitachi VSP disk arrays. Again, the only picture I can find shows the internals of the device. As with the Sharks, we bought two arrays and used the second one as a mirror of the primary array in the backup data center.

The Hitachi VSP was replaced in March 2015 by a Hitachi VSP G1000. The new array was purchased and maintained by ITS Storage, so I don’t have any pictures. The VSP G1000 was replaced by the current IBM DS8882F in February 2020.