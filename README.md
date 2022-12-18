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

## Diagnostic Cards

The Lisa is a veritable hassle to work on due to the nature of its construction; as it uses a backplane (referred to as the "motherboard" by Apple) to connect all the separate system cards, the entire "card stack" or "card-cage" must be assembled and inserted into the system chassis for the Lisa to operate. These cards seek to address this difficulty by allowing one to a) extend the card cage outside of the system chassis by means of an umbilical cord of sorts, and b) fold the I/O and CPU cards over 90 degrees to allow the CPU card to be worked on by exposing its component side to the user. To keep manufacturing costs as low as possible, these cards are meant to be snapped apart by the end-user instead of producing multiple individual cards.

For the riser cards that flip the CPU and I/O cards over by 90 degrees, there is a recess between the edge of the cage and the slot used to align the I/O card that almost perfectly allows for flipping the cards and having just enough distance left over for the CPU card to insert into the new edge connector. The distance is so exact that it makes me wonder if Apple didn't use a similar set of cards of their own for testing/diagnosing Lisa hardware.

## Drop-In ATX PSU Replacement

The Lisa's PSU is, if unmaintained, virtually unreparable at this point if any of a few issues are encountered. Certain components in the crowbar circuit, the relay used to soft-power-up the system, the main transformer itself, and some of the transistors are no longer manufactured and next to impossible to locate replacements for. This PCB aims to be a drop-in replacement for the original PSU and uses as many off-the-shelf components as possible. Eventually, I'd like to return to this once my knowledge of PSU design has matured a bit and put together a much less overkill (and better) approach.