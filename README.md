# Repository overview
In this repository schematics, layout and gerber files are shared for the recreation of an interposer PCB allowing upgraded Intel CPUs to be used on the original Xbox console. The designs are made in KiCAD.

# Background
Back in 2003 the Taiwanese company FRIENDTECH came up with methods to upgrade computer systems with faster CPUs, and the original Xbox was among the devices for which they offered an upgrade path. Details of their solution can be found in their patent application https://patents.google.com/patent/US20050282621A1/en.

This _interposer board_ follows the same schematic, minus the poorly functioning clock reduction circuitry, and with the BGA footprint positioned to allow use of the original heatsink mounting holes.

# Attribution
This board is a recreation of the original FRIENDTECH design. Revision 1 was a board-level clone of original design through intermediate clones by 'trusty', 'N64freak' and 'Kekule'. Revisions 2 and 3 are re-routed from scratch, inspired by pictures of a similar board with cleaner layout by @gaasedelen.

# Usage (TODO)
Inspect [BOM](https://htmlpreview.github.io/?https://raw.githubusercontent.com/zzattack/xbox-cpu-interposer/main/kicad/bom/ibom.html) for an overview of required capacitors/resistors.
Installation guide will be added later.

# Status
Full schematic and PCB are routed. Gerber files are available in the Github releases overview.

**PCB IS STILL IN PRODUCTION FOR TESTING **

![rev3](https://github.com/zzattack/xbox-cpu-interposer/assets/835006/c596aff5-cd8c-410e-8c1b-4faabdb0f6b3)
![rev3_front](https://github.com/zzattack/xbox-cpu-interposer/assets/835006/1258fd54-7280-47a1-85a4-16bc3697e153)
![rev3_back](https://github.com/zzattack/xbox-cpu-interposer/assets/835006/35adea4f-2954-4cf9-9112-bbc7521c0003)

