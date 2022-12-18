# Lisa Hardware

This project aims to either reproduce or provide alternative designs for internal electronic and logical elements of the Apple Lisa 2. Any references to part availability are current as of late 2022.

# Project Elements

The following sections provide detail for the elements this project aims to either reproduce or replace. Due to the current component shortage, pre-assembled vendor carts are not provided as component availability is constantly in flux.

## CPU Card

The Lisa 2's CPU hardware is contained on a single dedicated PCB in the card stack. This card contains sub-sections responsible for the following aspects of the Lisa 2:

- The CPU itself;
- Error detection logic;
- Memory management;
- Video signal generation, timing, and VRAM management;
- Clock circuitry; and
- Minor I/O functionality.

The CPU card interfaces with the system bus via a 120-pin card edge connector whose pins are 1.4mm wide across a 2.54mm pitch, using a readily available and currently produced female connector on the motherboard (backplane). There are three factory bodge wires and one undocumented ceramic disc capacitor which have now been integrated directly into the design of this card. The original traces which were cut in order to produce the bodges have been removed and are replaced by the connections the bodges were added to create. The capacitor has been added with its own component designation (C43) and silkscreen in order to prevent users from having to solder the capacitor directly to the IC's legs on which it was originally soldered. Additionally, some passive components listed in the schematics are not present on the original hardware and, thus, are also not present on this card. These and other corrections/errata may be found in the CPU card sub-directory within the readme file.