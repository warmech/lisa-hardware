# Lisa 2 CPU Card

This project seeks to reproduce the Lisa 2 CPU card as faithfully to the original layout as possible. All ICs, traces, and silkscreening are located as close as possible to their original positions on an OEM card and the most absolute minimum of changes have been applied. These changes can be found in the section below titled "Modifications".

## Resources Found In This Project

In this project, you will find miltuple directories containing different project components. These include:

1. Original EasyEDA project data for import into your EasyEDA client (if you use that particular EDA software).

2. Exported Altium-equivalent project data; EasyEDA explicitly states that that feature is still in beta and may produce unexpected results when imported - caveat utilitor.

3. Gerber files for the current board revision; these may be uploaded to the PCB manufacturer of your choice for production.

4. Scans of the original CPU card that was generously donated for the purposes of completing this project. These are of more than acceptable quality and allow for easy observation and study of the OEM card's architecture. An indicator for length is included in the scans to indicate how the image should be properly scaled on your display to accurately reflect actual size.

5. Schematics exported from EasyEDA which detail the PCB design; each major section of the PCB is contained in a separate PDF.

6. Preview images of the final Gerber output.

# Errata, Corrections, and Modifications

## Factory Bodges

The following bodges have been corrected in this card's design to be included as physical traces which remove the original incorrect traces altogether and replace them with the correct required traces.

1. Original Connection: U1D_12 > U2D_4
   Corrected Connection: U1D_11 > U2D_4

2. Original Connection: U3C_2 > U5D_14
   Corrected Connection: U1D_2 > U5D_14

3. Original Connection: U4A_4 > U2B_3
   Corrected Connection: U1B_8 > U2B_3

## Components Not Featured On PCB

1. R18 (1K) which, in the schematics pulls up the line between U3C_1, U3B_13, U3B_5, U3C_15, U3B_3, U4B_5, U4B_3, U2B_5, U4B_11, U4B_3, U2B_1, U4B_15, U2B_11, and U2B_13, is not present on the CPU card revision this design was based off of (620-0119 Rev. H). RP1_5 is also connected to this network and seems to fulfill a similar purpose.

2. R19 (3.3K) which, in the schematics pulls up the VMA line between U13A_19 (CPU pin 19) and U8C_8 (74LS244 pin 8), is not present on the CPU card revision this design was based off of (620-0119 Rev. H).

3. DS1 which, in the schematics is an LED tying U11C_2 to GND, is not present on the CPU card revision this design was based off of (620-0119-H). It is present on some other revisions, however.

## Schematic Errata

1. Some versions of the schematics indicate connector pins 1 and 2 are /SH0 and /SL0 respectively. These are backwards (pin 1 should be /SL0 and pin 2 should be /SH0) and corrected in later printings of the schematics.

2. Four pins on RP1 are connected incorrectly in the schematic to a family of signal lines:
   - RP1_1 shows to be tied to the /RO line in the schematics; it is actually tied to the /IO line
   - RP1_14 shows to be tied to the /IO line in the schematics; it is actually tied to the /RO line
   - RP1_9 shows to be tied to the /MEM line in the schematics; it is actually tied to the /STK line
   - RP1_25 shows to be tied to the /STK line in the schematics; it is actually tied to the /MEM line

3. U11C_3 shows to be tied to the UD7 line in some versions of the schematics. It is instead tied to U11C_4/GND on the CPU card revision this design was based off of (620-0119 Rev. H).

## Modifications

1. The ceramic disc capacitor bridging U5C_11 (/HDMSK) to U5C_8 (GND) was originally soldered straight to the pins of the IC. This has been removed and added as a distinct component with a designated number and mask - C43 - and is located adjacent and in parallel to C21.

2. The three unpopulated pins to the right of U14D_23 (EPROM) are shown in the schematics as an undesignated jumper between the UA12 line and +5V. The default configuration is a connection between U13A_40 and U13D_23/U14D_23. A numerical designator and mask have been added - J1 - and the pads resized to accept standard 2.54mm pitch male header pins.

## Board Revisions

1. Version 1.0 of this PCB failed to connect the power and ground pins of U5A to their corresponding rails. This is corrected in version 1.1.
