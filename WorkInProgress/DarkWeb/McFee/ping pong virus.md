- Ping-Pong virus

  From Wikipedia, the free encyclopedia

  [Jump to navigation](https://en.wikipedia.org/wiki/Ping-Pong_virus#mw-head)[Jump to search](https://en.wikipedia.org/wiki/Ping-Pong_virus#searchInput)

  | ![img](https://upload.wikimedia.org/wikipedia/commons/thumb/a/a4/Text_document_with_red_question_mark.svg/40px-Text_document_with_red_question_mark.svg.png) | This article includes a [list of references](https://en.wikipedia.org/wiki/Wikipedia:Citing_sources), related reading or [external links](https://en.wikipedia.org/wiki/Wikipedia:External_links), **but its sources remain unclear because it lacks [inline citations](https://en.wikipedia.org/wiki/Wikipedia:Citing_sources#Inline_citations)**. Please help to [improve](https://en.wikipedia.org/wiki/Wikipedia:WikiProject_Fact_and_Reference_Check) this article by [introducing](https://en.wikipedia.org/wiki/Wikipedia:When_to_cite) more precise citations. *(February 2014)* *([Learn how and when to remove this template message](https://en.wikipedia.org/wiki/Help:Maintenance_template_removal))* |
  | ------------------------------------------------------------ | ------------------------------------------------------------ |
  |                                                              |                                                              |

  | [![Virus-ping-pong.jpg](https://upload.wikimedia.org/wikipedia/commons/thumb/c/cd/Virus-ping-pong.jpg/240px-Virus-ping-pong.jpg)](https://en.wikipedia.org/wiki/File:Virus-ping-pong.jpg) |                                                              |
  | :----------------------------------------------------------- | ------------------------------------------------------------ |
  | Aliases                                                      | Boot, Bouncing Ball, Bouncing Dot, Italian, Italian-A, VeraCruz, Ping-Pong.A, Ping-Pong.B, Ping-Pong.C |
  | Type                                                         | [Computer virus](https://en.wikipedia.org/wiki/Computer_virus) |
  | Subtype                                                      | [Boot sector virus](https://en.wikipedia.org/wiki/Boot_sector_virus) |
  | Author(s)                                                    | Unknown                                                      |
  | [Operating system(s)](https://en.wikipedia.org/wiki/Operating_system) affected | [DOS](https://en.wikipedia.org/wiki/DOS)                     |

  The **Ping-Pong virus** (also called **Boot**, **Bouncing Ball**, **Bouncing Dot**, **Italian**, **Italian-A** or **VeraCruz**) is a [boot sector virus](https://en.wikipedia.org/wiki/Boot_sector_virus) discovered on March 1, 1988, at the *[Politecnico di Torino](https://en.wikipedia.org/wiki/Politecnico_di_Torino)* (Turin Polytechnic University) in [Italy](https://en.wikipedia.org/wiki/Italy). It was likely the most common and best known boot sector virus until outnumbered by the [Stoned](https://en.wikipedia.org/wiki/Stoned_(computer_virus)) virus.

  ## Replication method[[edit](https://en.wikipedia.org/w/index.php?title=Ping-Pong_virus&action=edit&section=1)]

  Computers could be contaminated by an infected diskette, showing up as a 1 [KB](https://en.wikipedia.org/wiki/Kilobyte) [bad cluster](https://en.wikipedia.org/wiki/Cluster_(file_system)) (the last one on the disk, used by the virus to store the original [boot sector](https://en.wikipedia.org/wiki/Boot_sector)) to most disk checking programs. Due to being labelled as bad cluster, [MS-DOS](https://en.wikipedia.org/wiki/MS-DOS) will avoid overwriting it. It infects disks on every active drive and will even infect non-bootable [partitions](https://en.wikipedia.org/wiki/Disk_partitioning) on the hard disk. Upon infection, the virus becomes memory resident.

  ## Effect[[edit](https://en.wikipedia.org/w/index.php?title=Ping-Pong_virus&action=edit&section=2)]

  The virus would become active if a disk access is made exactly on the half-hour and start to show a small "ball" bouncing around the screen in both [text mode](https://en.wikipedia.org/wiki/Text_mode) (the [ASCII](https://en.wikipedia.org/wiki/ASCII) [bullet](https://en.wikipedia.org/wiki/•) character "•") and graphical mode. No serious damage is incurred by the virus except on '286 machines (and also V20, '386 and '486), which would sometimes crash during the ball's appearance on the screen. The cause of this crash is the "`MOV CS,AX`" instruction, which only exists on '88 and '86 processors. For this reason, users of machines at risk were advised to save their work and reboot, since this is the only way to temporarily get rid of the virus.

  The original Ping Pong virus (Ping-Pong.A) only infects [floppy disks](https://en.wikipedia.org/wiki/Floppy_disk). Later variants of this virus such as Ping-Pong.B and Ping-Pong.C also infect the hard disk boot sector as well. While the virus is active, one cannot replace the boot sector—it either prevents writing to it or it immediately re-infects it.

  Ping-Pong.A is extinct but the hard-disk variants can still appear.

  ## References[[edit](https://en.wikipedia.org/w/index.php?title=Ping-Pong_virus&action=edit&section=3)]

  - ["Virus Descriptions : Ping-Pong"](http://www.f-secure.com/v-descs/pingpong.shtml). F-Secure. Retrieved June 6, 2006.
  - ["SmartDefense Research Center"](https://web.archive.org/web/20071026044230/http://vic.zonelabs.com/tmpl/body/CA/virusDetails.jsp?VId=7633). Zone Labs. 2002. Archived from [the original](http://vic.zonelabs.com/tmpl/body/CA/virusDetails.jsp?VId=7633) on October 26, 2007. Retrieved June 6, 2006.

  | hide[v](https://en.wikipedia.org/wiki/Template:Hacking_in_the_1980s)[t](https://en.wikipedia.org/wiki/Template_talk:Hacking_in_the_1980s)[e](https://en.wikipedia.org/w/index.php?title=Template:Hacking_in_the_1980s&action=edit)Hacking in the 1980s |                                                              |
  | -----------------------------------------------------------: | ------------------------------------------------------------ |
  | ← —[Timeline](https://en.wikipedia.org/wiki/Timeline_of_computer_security_hacker_history#1980s)[1990s](https://en.wikipedia.org/wiki/Template:Hacking_in_the_1990s) → |                                                              |
  |          [Individuals](https://en.wikipedia.org/wiki/Hacker) | [The Analyzer](https://en.wikipedia.org/wiki/Ehud_Tenenbaum)[Markus Hess](https://en.wikipedia.org/wiki/Markus_Hess) |
  |             [Malware](https://en.wikipedia.org/wiki/Malware) | [1260](https://en.wikipedia.org/wiki/1260_(computer_virus))[Brain](https://en.wikipedia.org/wiki/Brain_(computer_virus))[Byte Bandit](https://en.wikipedia.org/wiki/Byte_Bandit)[Cascade](https://en.wikipedia.org/wiki/Cascade_(computer_virus))[Christmas Tree EXEC](https://en.wikipedia.org/wiki/Christmas_Tree_EXEC)[Elk Cloner](https://en.wikipedia.org/wiki/Elk_Cloner)[Father Christmas](https://en.wikipedia.org/wiki/Father_Christmas_(computer_worm))[Ghostball](https://en.wikipedia.org/wiki/Ghostball_(computer_virus))[Jerusalem](https://en.wikipedia.org/wiki/Jerusalem_(computer_virus))[Lamer Exterminator](https://en.wikipedia.org/wiki/Lamer_Exterminator)[Morris worm](https://en.wikipedia.org/wiki/Morris_worm)Ping-Pong[SCA](https://en.wikipedia.org/wiki/SCA_(computer_virus))[Scores](https://en.wikipedia.org/wiki/Scores_(computer_virus))[Stoned](https://en.wikipedia.org/wiki/Stoned_(computer_virus))[WANK Worm](https://en.wikipedia.org/wiki/WANK_(computer_worm)) |

  [Categories](https://en.wikipedia.org/wiki/Help:Category): 

  - [Boot viruses](https://en.wikipedia.org/wiki/Category:Boot_viruses)
  - [Hacking in the 1980s](https://en.wikipedia.org/wiki/Category:Hacking_in_the_1980s)