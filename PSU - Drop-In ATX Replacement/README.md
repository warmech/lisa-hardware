# Drop-In ATX PSU Replacement

This PCB aims to serve as a replacement for the aging 1.2A Lisa PSU. The original 1.2A power supply uses a number of components that are becoming increasingly more difficult to obtain, namely:

- Transistors in the power regulation and crowbar circuits
- The solid state optoelectronic relay used to switch on power in the PSU
- The central transformer (which had failed in one of mine)

The following components/parts are required and may be divided into two types: new components/parts and parts which may otherwise be recycled from an original PSU.

## New Components/Parts

- An ATX PSU whose PCB is no taller than XXmm and is capable of outputting +5V, -5V, +12V, and -12V
- A buck-boost converter that is capable of outputting at least 33VDC; these are inexpensive and widely available on retail outlets such as Amazon
- A 40mm fan (optional; 5V and 12V fans are both acceptable)
- A 2N4401 transistor
- A 40 KOhm resistor
- Four nylon or plastic standoffs - these are required to slightly lift the ATX PSU PCB off of the drop-in board
- Four small machine screws to secure the ATX PSU PCB to the drop-in board

## Recyclable Components/Parts

- The two potentiometers used in the brightness and contract circuit; these may be acquired in a newer, smaller form factor if yours are damaged or missing
- Resistors 1, 2, 3, 4, 5, 6, and 7 used in the brightness and contract circuit
- The three pin Molex connector for the AC input lines

# Assembly Instructions

The following instructions will guide you through the process of installing an ATX PSU into a Lisa PSU enclosure:

1. Begin by removing the ATX PSU's PCB from its metal housing. You may need to cut or desolder the following components to remove the board from the case:
  * The IEC connector - be sure to make a note of where the hot and neutral lines terminate on the PCB; you will need to reconnect these later to the drop-in PCB exactly the same as they were wired originally. In North America (the United States in particular), the hot line will usually be black in single-phase AC wiring and the neutral line will be white; in Europe (specifically) and other regions, the hot line is typically brown and the neutral line is blue. It is not uncommon to find AC wiring in consumer electronics in the US to have European coloring, so be mindful of what colors you are working with when opening an ATX PSU. Additionally, AC ground wiring (sometimes referred to as FG, or, floating ground) will almost always be either solid green or green with a yellow stripe in all regions and locales.
  * The AC voltage selector switch - prior to disconnecting this switch, be sure to test continuity for the switch settings with a multimeter. Depending on your region, your PSU will require either 110/115/120V or 220/230/240V AC; make sure that the switch is set to the correct setting and record whether there is continuity between the contacts or not. If there is, and the switch is set to 110/115/120V, then you will need to solder the two wires that originally were connected to the switch to the two pads labelled "110V" on the drop-in PCB. If there is no continuity, and the switch is set to 220/230/240V, the two wires will need to be soldered to the pads labelled "220V". In the event that the switch is set to 220V and there IS continuity, solder the wires to the 110V pads instead in order to maintain continuity.
  * The PSU fan - this may or may not be directly soldered to the ATX PSU's PCB. If it is, proceed with desoldering it; if it is not soldered, disconnect it or desolder the connector from the PSU to remove it.
  * The power switch - some ATX PSUs were equipped with a manual power switch which serves as a kind interlock. If yours has one, test the switch's wiring for continuity when set to "on" (closed) and record the result; once recorded, desolder the switch. When installing the PSU on to the drop-in board, ensure that the wires are either soldered together (or not) to match the continuity of the switch when in the on/closed position.

2. Once the PSU has been removed from the case, proceed with desoldering the wiring harness connections; higher current power (and ground) rails will have potentially several wires to desolder. As you are desoldering, be sure to note which power rails ar soldered where. Some PSU PCBs note which sections of pads correspond to which voltages, but some do not. Once you have completed this step, you should have a PCB with:
  * No power or DC ground lines attached
  * A set of either black/white or brown/blue hot and neutral wires left in place
  * A set of two wires for setting input voltage left in place
  * (Optional) A set of two wires for manually engaging the PSU power interlock

3. Set the PSU on top of the drop-in card and align is four mounting holes with the corresponding holes in the drop-in card. Once aligned, determine the (approximate) distance between the power/ground pads on the ATX PCB and the corresponding pads on the drop-in card. Once you have determined this distance, use the wire harness removed in step two to produce the following quantities of wire at the appropriate length:
  * Six (6) ground wires
  * Four (4) +5V wires
  * Three +12V wires
  * One (1) -5V wire
  * One (1) -12V wire
  * One (1) 5VSB (standby power) wire
  * One (1) wire to connect the PS_ON signal from the ATX PCB to the drop-in card

4. Once the wires have been produced, solder one end in place on the ATX PSU and the other end into the corresponding pad on the PCB.

5. Solder the AC voltage selector wires into their appropriate pads on the PCB.

6. If recycling components from the original Lisa PSU, remove them from the original PSU and solder them in place now and install all remaining components.

7. Install the PSU into the Lisa PSU case and attach the IEC power connector. Once secured, screw the case back together to finish.
