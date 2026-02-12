# ObiWanStenobit – Build Guide

This document describes the complete build process for the **ObiWanStenobit (OWS)** keyboard, from PCB preparation to firmware flashing and initial steno setup.

![Final result](/docs/images/b00.jpg)

## Bill of Materials

The following table lists all required and optional components needed to build a complete ObiWanStenobit keyboard compatible with the provided case.

| Ref. | Component        | Description                 | Quantity | Links |
|------|------------------|-----------------------------|----------|-------|
| 1    | PCBs             | OWS panelized full set      | 2        | [Gerbers](/hardware/pcb/gerber) |
| 2    | RP2040           | Pro Micro edition 16M       | 1        | [Aliexpress](https://it.aliexpress.com/item/1005009348943760.html) |
| 3    | Socket           | M2F 12-pin[^1]              | 2        | [Aliexpress](https://it.aliexpress.com/item/1005007476809536.html) |
| 4    | Pins             | MCU header pins[^1]         | 24       | [Aliexpress](https://it.aliexpress.com/item/1005010342280815.html) |
| 5    | Kailh switches   | Choc V1 (or V2)             | 30       | [Aliexpress](https://it.aliexpress.com/item/1005008883418065.html) |
| 6    | PJ-320A          | THT TRRS jack socket[^2]    | 8        | [Aliexpress](https://it.aliexpress.com/item/1005007334594658.html) |
| 7    | Tactile switch   | SMD 2-pin 4x3x2mm          | 1        | [Aliexpress](https://it.aliexpress.com/item/1005010586092874.html) |
| 8    | Diode            | DO-35 1N4148                | 30       | [Aliexpress](https://it.aliexpress.com/item/32947233235.html) |
| 9    | TRRS cables      | Male-to-male TRRS cable[^2] | 4        | [Aliexpress](https://it.aliexpress.com/item/32462922130.html) |
| 10   | Pins             | M2M header pin              | 6        | [Aliexpress](https://it.aliexpress.com/item/4000988113226.html) |
| 11   | Keycaps          | Compatibles with Choc V1    | 30       | [STL](/hardware/case/stl) / [Aliexpress](https://it.aliexpress.com/item/1005009100305250.html) |
| 12   | Case             |                             | 1        | [STL](/hardware/case/stl) |
| 13   | Screws           | M2x4mm cylindrical head PH  | 8        | [Aliexpress](https://it.aliexpress.com/item/32971605141.html) |
| 14   | Screws           | M2x10mm cylindrical head PH | 2        | [Aliexpress](https://it.aliexpress.com/item/32971605141.html) |
| 15   | Nuts             | M2 hex                      | 10       | [Aliexpress](https://it.aliexpress.com/item/1005007796257329.html) |
| opt. | Rubber feet      |                             | 8        | [Aliexpress](https://it.aliexpress.com/item/1005002619943801.html) |
| opt. | Nut              | 1/4in-20                    | 1        | |
| opt. | Paracord         | 550                         | 50cm     | [Aliexpress](https://it.aliexpress.com/item/4000176073490.html) |
| opt. | Spring buckle    |                             | 1        | [Aliexpress](https://it.aliexpress.com/item/1005003036732343.html) |

[^1]: To socket the MCU as low as possible, the use of Mill-Max pin headers is recommended.

[^2]: TRRS connectors (4 rings) are required.

## Required and Recommended Tools

### Required tools

- Soldering iron
- Solder wire
- Flush cutters
- Pliers
- Tweezers
- Fine-grit sandpaper

### Recommended tools

- Flux

## Terminology and PCB Nomenclature

The following terminology is used throughout this guide:

- **Main Keyboard PCB**: the primary PCB hosting the majority of switches (left and right)
- **2-Key Expansion PCB**: the auxiliary PCB hosting the additional two keys
- **Controller PCB**: the PCB hosting the microcontroller and connectors

## PCB Preparation

Separate all PCBs by breaking the mouse bites from two full PCB sets.  
One extra Controller PCB will remain unused.

![2 full sets of PCBs](/docs/images/b01.jpg)

Place a sheet of fine-grit sandpaper on a flat surface and gently sand the PCB edges to remove mouse bite remnants.  
Edges should be smooth to the touch.

![Before and after edge sanding](/docs/images/b02.jpg)

## Controller Preparation

This section is based on the guide provided for the Aurora series by [splitkb.com](https://splitkb.com/).  
Refer to the [original documentation](https://docs.splitkb.com/product-guides/aurora-series/build-guide/microcontrollers#using-mill-max-pins) for additional images.

Using sockets allows the microcontroller to be removed or replaced if necessary.  

Before starting, identify the correct controller orientation.  
The MCU is mounted above the **ivndbt.com** logo, with the chip facing the user.

Insert the sockets into the controller PCB and solder **one pin per socket** first.  
Check alignment carefully: if needed, reheat the joint and adjust.  
Once aligned, solder the remaining outer pins.

Before inserting the header pins, place a thin **plastic barrier** over the sockets to prevent solder from flowing inside them.  
Kapton tape is recommended, but a piece of sturdy plastic is fine too.
Failing to do this step can permanently solder the controller to the sockets, making removal nearly impossible.

Insert the header pins into the sockets one by one, pushing them fully.  

![Socket with plastic shield and pins in place](/docs/images/b03.jpg)

Place the microcontroller onto the pins and solder it in place.

![nice!nano position](/docs/images/b04.jpg)

The image shows a nice!nano controller, but the procedure is identical for the RP2040. If your pins are too long, cut them with the flush cutter.

![Socket with plastic shield and pins in place](/docs/images/b03a.jpg)
![RP2040 position](/docs/images/b04a.jpg)
![RP2040 soldered with long pins](/docs/images/b04b.jpg)
![RP2040 pins cut](/docs/images/b04c.jpg)

>The two holes near the USB connector must not be soldered in both cases.

After soldering, carefully remove the plastic layer.  
Take care not to bend the controller pins when mounting or removing the MCU.

## Controller PCB

Complete the controller PCB by soldering:

- The reset button
- The four TRRS jack sockets

![Complete Controller PCB](/docs/images/b05.jpg)

## Main Keyboard

### Soldering the PCBs

Place the Main Keyboard PCB and the 2-Key Expansion PCB on a flat surface with the switch side facing up.  
Align the edges carefully and solder the interconnecting pads generously.

![Frontside connection](/docs/images/b06.jpg)

Flip the PCB assembly and solder the pads on the backside as well.

![Backside connection](/docs/images/b07.jpg)

For improved mechanical strength, it is recommended to embed a square-section header pin into each of the thin interconnection pads **on the backside**.
To do this, reheat the solder and gently place the pin into position. Add solder if necessary to secure it.

![Backside reinforced connection](/docs/images/b08.jpg)

### Diodes

Identify diode polarity.  
The line printed on the PCB marks the cathode and must align with the line on the diode.

Bend the diode leads as close as possible to the diode body before insertion.  

![Diodes preparation](/docs/images/b09.jpg)

Solder all diodes on the front side of the PCBs and cut the exceeding leads.

![Diodes soldered](/docs/images/b10.jpg)

### Jack Sockets and Solder Jumpers

On the front side of the PCBs, place and solder all jack sockets.

Solder **only the solder jumpers on the backside of both PCBs**.  
The solder jumpers on the front side **must not** be soldered.

![Backside closeup of the PCB solder jumpers](/docs/images/b11.jpg)

### Keyswitches

Insert Kailh Choc switches into the PCB.

- Choc V2 switches will click into place
- Choc V1 switches will sit loosely until soldered

Solder all switch pins.

![Solder work finished](/docs/images/b12.jpg)

## Firmware Flashing

Prepare the firmware (QMK or ZMK) and flash it to the microcontroller following the instructions on the respective repositories:

- QMK: [qmk/qmk_firmware](https://github.com/qmk/qmk_firmware/tree/master/keyboards/ivndbt/ows)
- ZMK: [ivndbt/zmk-config-obiwanstenobit](https://github.com/ivndbt/zmk-config-obiwanstenobit)

### Testing

Connect each keyboard half to the Controller PCB.  
The ObiWanStenobit logo should face the user, and the USB connector should face away, as shown in the reference image.

![Connecting PCBS](/docs/images/b13.jpg)

Test the key matrix and verify correct left and right side behavior.

## Keycaps and Case

Print the case, holder, and keycaps using the provided [STL files](/hardware/case/stl).  
Sand edges if necessary.

> When printing the Main Keyboard PCB case, insert a G-code pause just before the nut cage ceiling is printed.  
> Place the four nuts in position and resume printing.

![Slicer pause](/docs/images/b14.png)
![Nuts positioning](/docs/images/b15.jpg)

Assemble the printed case components and install the PCB assembly using:

- M2x4mm screws to fix Main PCBs to their case (8 screws in total)
- M2x10mm screws to make the Controller PCB bay

Place the keycaps.

![Keyboard completed](/docs/images/b16.jpg)

Optional:
- Apply rubber feet to the bottom of the case for stability
- For an ergonomic angle, glue a 1/4in-20 nut to the bottom of the case and mount it on a tripod or similar support

### Holder Assembly

Pass the paracord through the holder hole and install the spring buckle.  
Secure it with a knot and melt the cord ends to prevent fraying.

![Holder in use](/docs/images/b17.jpg)

## Plover Setup

Install Plover following the [official documentation](https://plover.wiki/index.php/Plover_software).

Configure the keyboard:

- When using QMK, select the **GeminiPR** protocol
- When using ZMK, select the **Keyboard** protocol and configure key bindings accordingly

Learning and practice resources:
- https://plover.wiki/index.php/Category:Learning_stenography
- https://didoesdigital.com/typey-type/

## Extras

When using a Bluetooth-capable controller (e.g. nice!nano), the keyboard can be made wireless by soldering a LiPo battery to the pads labeled **B+** and **B-** near the USB connector.

The recommended battery model is **301230**.  
Refer to the [official documentation](https://nicekeyboards.com/docs/nice-nano/) for details. 

> Note: This modification enables wireless communication between the MCU and the host device, but the four TRRS cables between the main PCBs and the controller PCB are still required.
