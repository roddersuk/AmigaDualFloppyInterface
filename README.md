# AmigaDualFloppyInterface
**Amiga 500 6A Dual Internal Floppy Drive Interface**
Not ready for release yet

![Interface PCB](/Docs/AmigaDualFloppyInterfaceBoard.png)

I have recently acquired an Amiga 500 and wanted to expand its capability by adding a Gotek drive but didn't want to lose the internal floppy drive. I soon came across some of the restrictions of the A500 design which basically meant that if you have the Gotek as the primary, bootable drive the internal floppy drive (df1) wouldn't work. I could have course have gone down the external floppy route but I didn't want all that stuff hanging out the back of the Amiga.

So I started this project with these objectives:
- To support two floppy drives internally to the A500
- To be able to switch which one is bootable
- For the second drive to always be available
- Not to require any irreversible change to the A500
- Not to have any connections out to the external drive port

There are a number of issues to overcome to achieve these objectives:
1. All of the needed signals need to be picked up from the motherboard
2. A motor control signal has to be generated for the second drive
3. A drive identification has to be generated for the second drive
4. Some means of switching between the drives needs to be devised

The design was created using KiCad, the project files are in the KiCad folder. Production ready files are provided in the KiCad/Gerber folder and PDF versions of the schematic and PCB are provided in the Docs folder.

For more information see the User Guide in the Docs folder.

