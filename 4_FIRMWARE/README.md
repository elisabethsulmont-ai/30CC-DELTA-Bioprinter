# Firmware

This machine runs a modified configuration of Marlin, on the knutwurst fork for Anycubic
Kossel printers. Only the two configuration files are published here. The firmware source
itself is not redistributed, since it is upstream work under GPL v3.

## Files

| File | What it is |
|---|---|
| `Configuration.h` | Machine geometry, board, extrusion, endstops |
| `Configuration_adv.h` | Advanced settings |

## How to build it

1. Download the upstream firmware:
   [knutwurst/Marlin-2-0-x-Anycubic-Kossel-Linear-Plus](https://github.com/knutwurst/Marlin-2-0-x-Anycubic-Kossel-Linear-Plus)
   The repository is named after the Plus, but it covers both machine sizes. The
   `KNUTWURST_KOSSEL_PLUS` option selects between them, and it is left disabled here.
2. Replace `Marlin/Configuration.h` and `Marlin/Configuration_adv.h` in that repository with
   the two files from this folder.
3. Compile and flash with PlatformIO.
4. After flashing, send these commands in this order:

```
M502
M500
G28
```

`M502` loads the values compiled into the firmware, `M500` writes them to the EEPROM, `G28`
homes the machine. Skipping this leaves the printer running on whatever was stored in the
EEPROM before, and none of the settings below will apply.

## Bed and zero position

The original print bed is removed for this set up. Only the bare metal disc is kept underneath, which is a matter of
taste rather than a technical requirement.

The delta distances and the zero position are calculated from the surface of that disc, plus
30 mm. That margin exists so that the tip can never reach the disc and crash the syringe
assembly into it.

## Settings

| | |
|---|---|
| Base | Marlin 2.0.5, knutwurst Anycubic Kossel fork |
| Board | Trigorilla 1.4 |
| Machine | Anycubic Kossel, standard size, `KNUTWURST_KOSSEL_PLUS` disabled |
| Kinematics | Delta |
| Diagonal rod | 218 mm |
| Delta radius | 97 mm |
| Printable radius | 60 mm |
| Print height | 125 mm |
| Bed probe | None, manual levelling |
| Extruders | 1 |
| Hotend thermistor | Disabled, `TEMP_SENSOR_0 998` |
| Cold extrusion | Enabled, `EXTRUDE_MINTEMP 0` |
| E steps per mm | 96 |
| Max E feedrate | 1000 mm/s |
| Max E acceleration | 3000 mm/s² |

## What was changed, and why

| Setting | Stock | Here | Why |
|---|---|---|---|
| `TEMP_SENSOR_0` | thermistor | `998` | there is no hotend, the sensor is replaced by a dummy so the firmware does not fault |
| `EXTRUDE_MINTEMP` | 170 | `0` | paste is extruded cold, the firmware must stop refusing to move E |
| `DELTA_PRINTABLE_RADIUS` | <!-- valeur d'origine, à retrouver dans le dépôt de knutwurst --> | `60` | reduced to avoid collisions between the syringe assembly and the towers |
| `DELTA_HEIGHT` | <!-- valeur d'origine --> | `125` | <!-- à compléter --> |

## Known limitation

The E steps per mm are still the stock value for the printer's original filament extruder.
They have not been calibrated for the syringe drive, so the commanded extrusion length does
not correspond to a known volume. Calibrating this is the first thing to do on a new build.

<!-- Élisabeth : si tu as calibré, remplace ce paragraphe par la procédure et la valeur.
     Si tu ne l'as pas fait, laisse-le : c'est honnête, et ça évite qu'on prenne 96 pour une
     valeur mesurée. -->
