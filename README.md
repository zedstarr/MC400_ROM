# MC400 ROM
Psion MC400 ROM preservation & archival repository

Backing up and storing ROM files from the technical marvel that is the Psion MC200/MC400 laptop from 1989 - full multi-tasking GUI in 256k of ROM running in 256k of RAM on a 7.68MHz 80C86 running for 40+ hours on 8 x AA cells with clickable touchpad, instant on and with full solid-state storage on Psion's proprietary SSDs too!

Commerically unsuccessful so very few hardware examples are around, many LCD screens are mechanically failing with age so ROM images are stored here in the name of retro-computing historical preservation. This early version of Psion's Epoc/Os (EPOC16) is an important part of the technical history of the progression in development of what would become EPOC32 then Symbian OS that went on to power the first wave of modern smartphones.

![MC400 System Screen showing RAM/ROM/System info](https://zedstarr.files.wordpress.com/2021/09/screen2021-09-21-105648.png)

V2.60F was the "MC WORD" version, the last official EPOC OS release from Psion for the SIBO MC400 from 1992, over 30 years old at the time of writing.

Inspiration for this endeavour came after seeing: https://github.com/Treeki/WindEmu - I would love to see the Psion MC400's GUI immortalised in some form of emulator too.

In Sep 2021 I removed the 2 x 28F010 Flash ROM chips from the Memory board of a dead MC400, and dumped the contents of each chip individually using the TL866 - but fouind no relevant/recognisable strings in either image...?

Some time later my subconscious dredged up a random factoid I must've read in the HDK some months before; "ASIC1 is always in 16-bit mode in the MC400" <lightbulb on>

The two 8-bit flash chips that I had imaged must share the address bus and provide high 8-bits and low 8 bits to the 16-bit data bus... I interleaved alternate bytes from each image into one blob and lo and behold I have an image of the ROM! ("interleave" utility I used is here - https://github.com/drojaazu/interleave ). Suddenly the ROM image makes a lot more sense - recognisable strings and the top 16 Bytes contain classic 8086 reset vector/bootstrap code that jumps to an address (they also contain the date in ASCII when the image was built (``30 36  30 38 39 32`` = 060892) and the Hex Bytes that correspond to 2.60F (``0F 26``) of the MC Word machine's release/version yay!) 

``
0003fff0  ea 00 00 00 c0 00 30 36  30 38 39 32 0f 26 de 60  |......060892.&.`|``  
``00040000``  

![MC400 System Screen running ROMDUMP.IMG](https://zedstarr.files.wordpress.com/2023/01/scr_romd.png)

# Resources

MC400 info
https://zedstarr.com/the-psion-mc400/

Psion documentation project
https://doc.psion.info/

The Last Psion
https://hackaday.io/project/161291-the-last-psion

**NOTE**: The original copyright in this work has passed from Psion (via Motorola Solutions) to Zebra Technologies Corp https://www.zebra.com/gb/en/about-zebra.html - the activities detailed here are driven by an appreciation of what was ground-breaking technology and a desire to preserve and archive details of the physical machines that were built at the time via emulation.
