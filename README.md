# MC400 ROM
Psion MC400 ROM repository

Backing up and storing ROM files from the technical marvel that is the Psion MC400 laptop from 1989 - full multi-tasking GUI in 256k of ROM running in 256k of RAM on a 7.68MHz 80C86 running for 40+ hours on 8 x AA cells with clickable touchpad and with SSDs too!

Commerically unsuccessful so very few hardware examples are around

v2.60F was the "MC WORD" version, the last official OS release from Psion

In Sep 2021 I removed the 2 x 28F010 Flash ROM chips from the Memory board, and dumped the contents of each chip individually using the TL866 - no  relevant/recognisable strings in either image...?

Some time later my subconscious dredged up a random factoid I must've read in the HDK some months before; "ASIC1 is always in 16-bit mode in the MC400" <lightbulb on>

The two 8-bit flash chips that I had imaged must share the address bus and provide high 8-bits and low 8 bits to the 16-bit data bus... I interleaved alternate bytes from each image into one blob and lo and behold I have an image of the ROM! ("interleave" utility I used is here - https://github.com/drojaazu/interleave ). Suddenly the ROM image makes a lot more sense - recognisable strings and the top 16 Bytes contain classic 8086 reset vector/bootstrap code that jumps to an address (they also contain the date in ASCII when the image was built (30 36  30 38 39 32 = 060892) and the Hex Bytes that correspond to 2.60F (0F 26) of the machine release/version yay!) 

0003fff0  ea 00 00 00 c0 00 30 36  30 38 39 32 0f 26 de 60  |......060892.&.`|
00040000

  
