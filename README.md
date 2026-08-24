# 30CC-DELTA-Bioprinter

An open source syringe bioprinter for the extrusion of viscous biomaterials.
The engineering was developed with Ilias Poutsiakas ([github.com/iliasPts](https://github.com/iliasPts)).

The machine is built on an Anycubic Kossel Linear, a stock delta printer. The first step is
to strip it down: everything comes off except the bare frame and the control board. The
hotend and its heating assembly are removed and replaced by a syringe extruder, designed
after the [300CC Extruder](https://www.thingiverse.com/thing:5215048) by Emmanuel Hugnot.

The stock firmware is replaced by an open source one. This is what makes the rest work: the
extrusion rates are rescaled for a plunger instead of a filament drive, the travel limits are
redefined around the syringe assembly, and everything tied to heating the nozzle is removed,
since nothing is heated here.

The syringe is a 30 cc glass barrel with a metal luer lock. This capacity is intended for
fine biomaterials in small volumes. The tip is mounted on the luer lock, so changing the tip
is enough to set the flow, and the machine can be matched to the viscosity of the material,
down to very fluid ones. Tips run from 0.31 to 2.69 mm inner diameter, 24G to 10G. The
extrusion is cold.

The design is inexpensive and every part can be found in a hardware store. The concept is to
make bioprinting accessible outside of laboratories. The machine has been explored so far
with one project, embedded printing in a Carbopol support bath. The recipe and the method are
in this repository.

!!!!!!!!!!!!This is a workshop machine, made for experimental work. It is not a laboratory instrument, it is certified for nothing and it is not intended for any medical use.!!!!!!!!!!!!

## What is in this repository

| Folder | What's inside |
|---|---|
| `3D files` | Parts to print, and the editable sources to modify them |
| `Components bill` | Everything to buy, with quantities and where to find it |
| `Assembly` | How to build it, step by step, with photos |
| `Firmware_marlin` | The two configuration files, and how to compile them |
| `Project examples` | Projects made with the machine, starting with Liquid Dreaming |

The order to follow: strip the printer down, print the parts from `3D files`, order what is
listed in `Components bill`, build it with `Assembly`, then flash the firmware from
`Firmware_marlin`. Once the machine runs, `Project examples` shows what has been done with it.


<img width="534" height="757" alt="DSCF9794-3" src="https://github.com/user-attachments/assets/68620e2d-9ea2-4a13-8952-54649a282f59" />


<img width="534" height="757" alt="DSCF9827-3" src="https://github.com/user-attachments/assets/c28ab3e3-f6e4-4cf1-b219-f8663db59b5a" />

___________________________________


