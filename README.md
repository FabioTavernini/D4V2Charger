# D4v2Charger

A work-in-progress proof of concept for adding built-in USB-C charging to the
[Emisar D4v2](https://intl-outdoor.com/emisar-d4v2-high-power-led-flashlight.html) flashlight, using a
pogo-pin connector in place of removing the cell to charge it externally.

## Status

Early prototype / proof of concept. Nothing here has been validated in a
final build yet — expect rough edges, and treat all files as subject to
change.

## How it works

- A small PCB sits inside the flashlight and charges the cell via a
  [TI BQ25185](https://www.ti.com/product/BQ25185) single-cell Li-ion linear
  charger (with integrated power path).
- Power comes in through a pair of spring-loaded pogo pins rather than a
  connector mounted directly on the PCB, so no permanent cutout is needed
  for a USB-C receptacle on the board itself.
- A custom pogo-pin connector part and a modified flashlight body/case were
  designed to accommodate the charging contacts.

## Repo contents

- `pcb/` — KiCad project for the charger board
  - `D4v2Charger.kicad_pro` / `.kicad_sch` / `.kicad_pcb` — schematic and PCB layout
  - `D4v2Charger.step` — 3D export of the finished board
  - `PogoPinConnector/` — FreeCAD model and STEP export of the pogo-pin connector
  - `D4v2Charger-backups/` — automatic KiCad backups (safe to ignore)
- `case/` — FreeCAD model of the modified flashlight body/case to fit the
  charging hardware

## Tools used

- [KiCad](https://www.kicad.org/) for schematic capture and PCB layout
- [FreeCAD](https://www.freecad.org/) for mechanical/case design

## Disclaimer

This is a hobbyist mod to a battery-powered lighting device. Modifying
charging circuitry and battery contacts carries fire/safety risk if done
incorrectly. Use at your own risk.

## License

Licensed under the [CERN Open Hardware Licence Version 2 - Strongly
Reciprocal](LICENSE) (CERN-OHL-S-2.0).
