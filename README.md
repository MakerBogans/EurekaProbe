# EurekaProbe

![top](https://user-images.githubusercontent.com/101759743/212232886-41792e27-531e-489f-abd1-f27bca22079c.PNG)

The EurekaProbe is a PCB based microswitch probe for CoreXY 3D printers. This project takes inspiration from [Klicky](https://github.com/jlas1/Klicky-Probe/), [Euclid](https://github.com/nionio6915/Euclid_Probe) and [QuickDraw](https://github.com/Annex-Engineering/Quickdraw_Probe).

The aim of this project is to synthesise some of the best ideas from those other projects and distill them into a highly reliable, simple, robust, cost effective and easy to source alternative.

EurekaProbe is initially developed to be paired with the [DirtyBird](https://github.com/MakerBogans/dirtybird) toolhead for Voron CoreXY printers, however can be adapted to to all other toolheads (AfterBurner, StealthBurner, etc).

Construction of EurekaProbe uses two identical PCBs which are magnetically coupled with countersunk 8x3 magnents. The PCBs are reversible, with one soldered as the Probe PCB and the other is attached onto the toolhead.

Operation of the probe uses Klicky based macros to ensure the probe correctly attaches from the dock before probing the bed.

## Assembly
- Solder microswitch to one of the PCBs
- Solder JST header to the other PCB
- Solder STMSO nuts to both PCBs
- Screw countersunk magents to PCBs via SMTSO nuts with Torx screws. Ensure you have mixed polarity across the pairs
- Attach toolhead PCB to carriage via M3x5 low profile bolts into heat inserts
- Attach probe PCB to probe housing via M3x5 low profile bolts into heat inserts

## BOM
- 2	* EurekaProbe PCB
- 4	* 8x3-3 Countersunk magnets [Aliexpress](https://www.aliexpress.com/item/1005001610172466.html)
- 4 * M2.5x5mm Torx countersunk screw [Aliexpress](https://www.aliexpress.com/item/33006942612.html)
- 4 * SMTSO-M2.5-2.5ET [Aliexpress](https://www.aliexpress.com/item/1005003780036815.html)
- 4 * M3x5mm low profile bolt [Aliexpress](https://www.aliexpress.com/item/33049052926.html)
- 4 * M3x5x4 heat inserts [Aliexpress](https://www.aliexpress.com/item/1005003314830904.html)
- 1 * Omron D2F [DigiKey](https://www.digikey.com.au/en/products/detail/omron-electronics-inc-emc-div/D2F-5/8593136)
- 1 * JST B2B-XH-A [Aliexpress](https://www.aliexpress.com/item/4000029861567.html)
