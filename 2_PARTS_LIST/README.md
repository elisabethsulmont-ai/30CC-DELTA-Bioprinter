# Components bill

Everything you need to buy or salvage to build one machine. Parts to 3D print are not listed
here, they are in the 3D files folder.

The list is in [parts.csv](parts.csv). GitHub renders it as a sortable table.

## How to read it

| Column | Meaning |
|---|---|
| `ref` | Internal reference, used in the assembly guide |
| `category` | Mechanics, Motion, Electronics, Fluidics, Fasteners, Consumables |
| `designation` | What the part is, in plain words |
| `specification` | The dimensions or values that actually matter |
| `qty` | Quantity for one machine |
| `supplier_example` | One place it can be bought, an example rather than an endorsement |
| `price_eur` | Indicative, excluding shipping |
| `critical` | `yes` if substituting this part changes how the machine behaves |
| `notes` | Substitutions that work, traps to avoid |

## Starting point

The parts list of Emmanuel Hugnot's [300CC Extruder](https://www.thingiverse.com/thing:5215048)
is a good skeleton and it is already online. Start from it, and note for each line whether the
part was kept, changed or dropped.

