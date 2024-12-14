# Repository overview
In this repository schematics, layout and gerber files are shared for the recreation of an interposer PCB allowing upgraded Intel CPUs to be used on the original Xbox console. The designs are made in KiCAD.

# Background
Back in 2003 the Taiwanese company FRIENDTECH came up with methods to upgrade computer systems with faster CPUs, and the original Xbox was among the devices for which they offered an upgrade path. Details of their solution can be found in their patent application https://patents.google.com/patent/US20050282621A1/en.

This _interposer board_ follows the same schematic, minus the poorly functioning clock reduction circuitry, and with the BGA footprint positioned to allow use of the original heatsink mounting holes.

# Contact
I can be contacted at frank@zzattack.org if you're looking to obtain PCBs or CPUs.

# Attribution
This board is a recreation of the original FRIENDTECH design. Revision 1 was a board-level clone of original design through intermediate clones by 'trusty', 'N64freak' and 'Kekule'. Revisions 2 and 3 are re-routed from scratch, inspired by pictures of a similar board with cleaner layout by @gaasedelen, who also kindly assisted in finding issues with early board revisions.

# Usage (TODO)
Inspect [BOM](https://htmlpreview.github.io/?https://raw.githubusercontent.com/zzattack/xbox-cpu-interposer/main/kicad/bom/ibom.html) for an overview of required capacitors/resistors.
Installation guide will be added later.

# Status
Full schematic and PCB are routed. Gerber files are available in the Github releases overview.
Revision 3.2 and onwards should be working correctly.
Prior revisions require PCB modifications and should be avoided.

![rev33](https://github.com/user-attachments/assets/d8233981-2106-4230-9c0e-d044785e6a47)
![rev33_front](https://github.com/user-attachments/assets/05504527-243f-45ee-9fd0-078bd46bd519)
![rev33_back](https://github.com/user-attachments/assets/97cba066-3ce7-4e8c-a13a-351d06dafa6e)
