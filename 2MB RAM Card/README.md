# 2MB SIMM-Based RAM Card

This project seeks to reproduce the Lisa 2 CPU card as faithfully to the original layout as possible. All ICs, traces, and silkscreening are located as close as possible to their original positions on an OEM card and the most absolute minimum of changes have been applied. These changes can be found in the section below titled "Modifications".

## Resources Found In This Project

In this project, you will find miltuple directories containing different project components. These include:

1. Original EasyEDA project data for import into your EasyEDA client (if you use that particular EDA software).

2. Exported Altium-equivalent project data; EasyEDA explicitly states that that feature is still in beta and may produce unexpected results when imported - caveat utilitor.

3. Gerber files for the current board revision; these may be uploaded to the PCB manufacturer of your choice for production.

4. Schematics exported from EasyEDA which detail the PCB design; each major section of the PCB is contained in a separate PDF.

5. Preview images of the final Gerber output.

# Errata, Corrections, and Modifications

## OEM Hardware Errata

In some OEM/aftermarket boards currently in circulation, between one and three ground connections are missing; as such, there have been a number of people over time that have reported non-functional cards assembled from blanks. This project has identified and added/corrected those connections; it has been confirmed with multiple users that the following should be checked and tied to ground on boards currently in circulation:

1. U1_8 - Pin 8 (/1K) of U1 (74S109)
2. U2_15 - Pin 15 (/2G) of U2 (74LS139)
3. U4_15 - Pin 15 (/G) of U4 (74LS157)

U4_15 seems to universally be the most common of the three in known instances; if you have assembled a Sun card from a blank PCB and it is not functioning, check U4_15 first. A bodge wire to U4_8 will do the job.

## Modifications

If you are unable to source 256Kx9 parity SIMMs, the following modifications can be performed to allow you to use a couple of alternatives. These are untested by myself - caveat utilitor - and come from users sigma7 and patrick at LisaList [(link to archived thread)](https://web.archive.org/web/20231031062244/https://lisalist2.com/index.php/topic,456.msg3284.html#new).

> The problem (possibly not the only one, but a major DRAM compatibility issue) is that the Lisa design implements 256 cycles per 4ms of refresh. DRAM chips larger than 256K x1 typically need more (eg. 512 cycles per 8ms), and so are not refreshed adequately. They may appear to work at first but will fail in a few minutes. A 256K x9 SIMM with 3 chips may be made with one 256K x1 chip (for the parity bit) and two 256K x4 chips. The 256k x4 chips probably (maybe always, IDK) require more than 256 cycles of refresh. I speculate that an over-performing part may still work if it hosts the video page. A modification was in the works to convert the SR design to "hidden" refresh to support most DRAM chips, but since 30 pin SIMMs of any size (and sockets) are no longer inexpensive, we really need a new memory board design that uses current RAM chips. TLDR: Check the DRAM chip's datasheet: if it specifies more than 256 cycles of refresh, it probably won't work in the SR board. -sigma7

> You should be able to use 1M x9 SIMMs, which were more common than the 256k types. Address line A9 (pin 18) must be tied low so that only 1/4 of the capacity is used. The upper half of the memory is not refreshed, but since it is not used, this is not critical. -patrick