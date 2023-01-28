# EurekaProbe

![top](https://user-images.githubusercontent.com/101759743/212232886-41792e27-531e-489f-abd1-f27bca22079c.PNG)

The EurekaProbe is a PCB based microswitch probe for 3D printers. This project takes inspiration from [Klicky](https://github.com/jlas1/Klicky-Probe/), [Euclid](https://github.com/nionio6915/Euclid_Probe) and [QuickDraw](https://github.com/Annex-Engineering/Quickdraw_Probe).

The aim of this project is to synthesise some of the best ideas from those other projects and distill them into a highly reliable, simple, robust, cost effective and easy to source alternative.

EurekaProbe is initially developed to be paired with the [DirtyBird](https://github.com/MakerBogans/dirtybird) toolhead for Voron CoreXY printers, however can be adapted to to all other toolheads (AfterBurner, StealthBurner, etc).

Construction of EurekaProbe uses two identical PCBs which are magnetically coupled with countersunk 8x3 magnents. The PCBs are reversible, with one soldered as the Probe PCB and the other is attached onto the toolhead.

Operation of the probe uses Klicky based macros to ensure the probe correctly attaches from the dock before probing the bed.

## Acknowledgements
Thank you to the [MakerBogans](https://github.com/MakerBogans) for supporting and assisting with development of this project.

## Assembly

![eurekacarriage](https://user-images.githubusercontent.com/101759743/212459111-ce22d553-6cc3-424f-a5b7-5ea85d2c19fa.jpg)

- Solder SMTSO nuts to both PCBs
- Solder microswitch to one of the PCBs
- Solder JST header to the other PCB
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

## Carriage mounts

__Coming soon__

## Probe docks

A dock is available and tested for the Voron Trident. It is compatible with Klicky style mounts and includes a fixed sidemount designed to suit the Trident with a Dirtybird toolhead carriage. Other printers are likely to work with the variable Klicky arm but are untested.

### Trident probe dock

![](Images/Trident%20dock%20cad.png)

Printed parts are pre-oriented for printing. Use your typical Voron part settings to print.

![](Images/Trident%20dock%20stls.png)

- 1 x [Eureka Dock](STLs/Eureka%20Dock.stl)
- 1 x [Eureka Trident Dock Arm](STLs/Eureka%20Trident%20Dock%20Arm.stl)
- 1 x [Trident Dock Sidearm](STLs/Eureka%20Trident%20Dock%20Sidearm.stl)

**BOM**

- 4 * M3x8mm SHCS
- 4 * M3x5x4mm heat inserts [Aliexpress](https://www.aliexpress.com/item/1005003314830904.html)
- 2 * M5x10mm BHCS
- 2 * M5 T-Nuts for 2020 extrusion
- 2 * 6mmx3mm round magnets

**Assembly**

![](Images/Trident%20dock.jpeg)

- Fit heat inserts into the dock arm and dock sidearm
- Screw the sidearm to the gantry arm using 2 x M3x8
- Fit 6x3 magnets into the side of the dock. It is normal for it to crack the top plastic slightly. If it has made the dock prone to breaking then the dock may need to be printed with a lower extrusion multiplier to allow more room for the magnets
- Screw the dock to the to the side arm using 2 x M3x8
- Insert the two t-nuts into the gantry extrusion
- Screw the dock to the gantry using 2 x M5x10

**Example klick configuration**

The Trident dock is designed to dock and undock the probe at the real left max units of the printer. On a Trident 250 this would be `X,Y = 0,250`. You are free to position the dock anywhere you like, this is what works for me.

Main `klicky-variables.cfg` changes required to get up and running.

```ini
# Set to 0 to have the probe move to center of bed
variable_z_endstop_x: 0
variable_z_endstop_y: 0

# Dock location
variable_docklocation_x:   0 # X Dock position
variable_docklocation_y: 250 # Y Dock position

# Dock move.
# Final toolhead movement to release the probe on the dock.
# Values are a relative move.
Variable_dockmove_x:   0
Variable_dockmove_y: -40
Variable_dockmove_z:   0

# Attach move.
# Final toolhead movement to attach the probe on the mount.
# Values are a relative move.
Variable_attachmove_x: -50
Variable_attachmove_y:   0
Variable_attachmove_z:   0

# Back off from Y endstop when homing to avoid accidentality
# docking the probe.
variable_home_backoff_y: 40
```

*Remember*: these values are a guide only. Follow the [Klicky-macros](https://github.com/jlas1/Klicky-Probe/tree/main/Klipper_macros) documentation when setting up the dock location for the first time.
