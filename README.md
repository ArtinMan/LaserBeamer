# LaserBeamer
'''My build: IMR18650 3.7V 1500mAh cell → USB-C charging via TP4056 (~1A charge rate) → DW01A + FS8205A protection → latching power switch → AP2112K-3.3 regulator → 532nm 5mW laser diode module. Green LED shows charging status.'''

#Few Concepts to know:
'''Schematic vs. PCB. The schematic is a logical diagram — what connects to what, regardless of physical size or position. The PCB is the physical board. Schematic always comes first.

Nets. A "net" is a name for a group of pins that are all the same electrical point. Same net name = connected, even without a drawn line between them.

Why so many capacitors. Small ceramic capacitors near a chip's power pins smooth out sudden current draw changes. Every IC here gets one nearby its power pin. Just place them close to the chip they support.

No-connect flags. Some chip pins are intentionally left unused in a given design. KiCad's Electrical Rules Checker (ERC) doesn't know that's intentional unless you tell it — you do that by placing a small "X" marker (a no-connect flag) directly on that pin. Skipping this doesn't break the circuit, but it clutters your ERC report with false warnings, making it harder to spot real problems.

Reference designators. U1, R3, J4, etc. — letter = part type, number = which one. Don't worry about matching numbers exactly to this guide; KiCad's Annotate step cleans these up automatically at the end.'''
