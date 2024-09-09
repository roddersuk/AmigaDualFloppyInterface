# AmigaDualFloppyInterface
**Amiga 500 6A Dual Internal Floppy Drive Interface**

![Interface PCB](/Docs/Board.png)

I have recently acquired an Amiga 500 and wanted to expand its capability by adding a Gotek drive but didn't want to lose the internal floppy drive. I soon came across some of the restrictions of the A500 design which basically meant that if you have the Gotek as the primary, bootable drive the internal floppy drive (df1) wouldn't work. I could have course have gone down the external floppy route but I didn't want all that stuff hanging out the back of the Amiga.

So I started this project with these objectives:
- To support two floppy drives internally to the A500
- To be able to switch which one is bootable
- For the second drive to always be available
- Not to require any unreversible change to the A500
- Not to have any connections out to the external drive port

There are a number of issues to overcome to achieve these objectives:
1. All of the needed signals need to be picked up from the motherboard
2. A motor control signal has to be generated for the second drive
3. A drive identification has to be generated for the second drive
4. Some means of switching between the drives needs to be devised

There is a readily available circuit to achieve 2. and 3. (see http://www.primrosebank.net/computers/amiga/upgrades/amiga_upgrades_storage_fd_con.htm) which needs the MTRX, IORESET and SEL1 signals as input and produces MTR1, RDY and INUSE as output. A common way to achieve switching is to add some circuitry under the EVEN CIA chip, which gives access to SEL0 and SEL1 but not MTRX, RDY, INUSE or IORESET. I decided instead to use the floppy interface which provides everything I need except MTRX and IORESET which I can pick up using flying probes to U36 and U37 respectively.

In order to provide switching I use a multiplexer chip (74LS157) to swap both SEL and MTR lines. Switching is effected by a single input being pulled to ground.

The design was created using KiCad, the project files are in the KiCad folder. Production ready files are provided in the KiCad/Gerber folder and PDF versions of the schematic and PCB are provided in the Docs folder.

