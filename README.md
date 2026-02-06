# ObiWanStenobit

Open-source steno keyboard with a pseudo-split layout, designed to be compact, portable, and cost-effective.

![ObiWanStenobit](/docs/images/a02.jpg)

## Overview

ObiWanStenobit is a 30-key, steno-oriented mechanical keyboard designed with the primary goals of low manufacturing cost and ease of transport.

The keyboard uses a pseudo-split architecture: it is physically split into two halves, but relies on a single microcontroller rather than the dual-controller setup typical of traditional split keyboards.

The PCB is panelized and kept under 100x100mm to reduce fabrication costs and allow the keyboard to be built from a single PCB order (minimum 2 units).

The provided 3D-printable case is designed to be easily closed and to protect switches and electronic components during transport, making the keyboard suitable for backpack travel.

More information about the design process and development history are available at [ivndbt.com](https://ivndbt.com/makes/ows/ows.html)

## Features

- Pseudo-split steno layout
- Single microcontroller design
- Panelized PCB (< 100x100mm)
- Pro Micro compatible controller
- Kailh Choc v1 and v2 switch support
- Compact and travel-friendly form factor
- Open hardware design

## Repository structure

- `hardware/pcb/`
  - KiCad project files
  - Manufacturing-ready Gerber files
- `hardware/case/`
  - FreeCAD source files
  - STL files for 3D printing
- `docs/`
  - Build guide (including BOM)
  - Images and additional documentation

## Hardware

### PCB

The PCB is designed in KiCad and provided both as source files and pre-generated Gerber files.  
Panelization is included in the design to minimize fabrication costs.

![PCB](/docs/images/a06.jpg)

### Case

The case is designed in FreeCAD.  
STL files provided in this repository should be considered the authoritative and up-to-date versions.
STLs hosted on [Printables]() are provided for convenience, but are not guaranteed to be updated to the latest revision.  

![Case](/docs/images/a05.jpg)

## Firmware

ObiWanStenobit is powered by both QMK and ZMK firmware.

- QMK: [ivndbt/qmk_firmware](https://github.com/ivndbt/qmk_firmware/tree/add-obiwanstenobit/keyboards/ivndbt/obiwanstenobit) (until merge with upstream)
- ZMK: [ivndbt/zmk-config-obiwanstenobit](https://github.com/ivndbt/zmk-config-obiwanstenobit)

Firmware is maintained in the respective upstream repositories.

## Build guide

Assembly instructions and the complete Bill of Materials are provided in:

- `docs/build-guide.md`

## License

This project is licensed under **CERN Open Hardware Licence v2 (CERN-OHL-S)**.

You are free to use, modify, manufacture, and distribute this project under the terms of the license.
Any redistribution should include proper attribution and a reference to the original source:

    Based on ObiWanStenobit by ivndbt, licensed under CERN-OHL-S v2.
    Source: https://github.com/ivndbt/obiwanstenobit

See the `LICENSE` file for details.

If you are interested in producing this design, creating variants, or collaborating, you are welcome to get in touch via the email address found at [ivndbt.com](https://ivndbt.com/#contact).

## Sponsors

PCB prototyping was sponsored by [PCBWay](https://www.pcbway.com/), who kindly manufactured and provided the prototype boards.

## References

- The ObiWanStenobit layout is inspired by [The Uni](https://stenokeyboards.com/products/the-uni-v4) from [StenoKeyboards](https://stenokeyboards.com/)
- The logo uses the [Kiwi Soda](https://fontenddev.com/fonts/kiwi-soda/) font from [fontenddev.com](https://fontenddev.com/)

