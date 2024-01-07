# Repository overview
In this repository schematics, layout and gerber files are shared for the recreation of an interposer PCB allowing upgraded Intel CPUs to be used on the original Xbox console. The designs are made in KiCAD.

# Background
Back in 2003 the Taiwanese company FRIENDTECH came up with methods to upgrade computer systems with faster CPUs, and the original Xbox was among the devices for which they offered an upgrade path. Details of their solution can be found in their patent application https://patents.google.com/patent/US20050282621A1/en.

This _interposer board_ follows the same schematic, minus the poorly functioning clock reduction circuitry, and with the BGA footprint positioned to allow use of the original heatsink mounting holes.

# Attribution
This board is a recreation of the original FRIENDTECH design. Revision 1 was a board-level clone of original design through intermediate clones by 'trusty', 'N64freak' and 'Kekule'. Revisions 2 and 3 are re-routed from scratch, inspired by pictures of a similar board with cleaner layout by @gaasedelen, who also kindly assisted in finding issues with early board revisions.

# Usage (TODO)
Inspect [BOM](https://htmlpreview.github.io/?https://raw.githubusercontent.com/zzattack/xbox-cpu-interposer/main/kicad/bom/ibom.html) for an overview of required capacitors/resistors.
Installation guide will be added later.

# Status
Full schematic and PCB are routed. Gerber files are available in the Github releases overview.

**PCB IS STILL IN PRODUCTION FOR TESTING **
Revision 3.2 is likely to work, since it incorporates the botches required to make a rev 3 board work.
Status will be updated when revision 3.2 is verified without additional modifications.
![rev32](https://github.com/zzattack/xbox-cpu-interposer/assets/835006/f559f9d4-ce14-4f04-a626-3b910d975016)
![rev32_front](https://github.com/zzattack/xbox-cpu-interposer/assets/835006/302c93cc-a5f9-4ede-8e5e-16e07123c849)
![rev32_back](https://github.com/zzattack/xbox-cpu-interposer/assets/835006/edec5145-ddb4-47ac-8176-b343b06281df)
