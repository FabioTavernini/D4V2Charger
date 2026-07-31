# Tools

Equipment needed to actually build and fit this board, beyond the parts in
[`BOM.csv`](./BOM.csv) and the design files in [`pcb/`](./pcb) and
[`case/`](./case). Software used to design the project (KiCad, FreeCAD) is
listed in the main [README](./README.md#tools-used).

## PCB assembly

The board is a 1.6mm, 2-layer design with parts on both sides, and the
smallest packages are the 0402 caps/resistors — hand-placing those without
a stencil is the fiddly part. Planned process: manual paste dotting +
hot plate reflow (no stencil ordered, board too small to justify it).

- Hot plate (cheap AliExpress hot plate + controller kit) as the reflow
  source. Heat conducts up through the board copper, so it also reflows
  the BQ25185's exposed thermal pad fine without needing hot air.
- Solder paste in a syringe with a fine (~22-25ga) blunt needle tip, for
  dotting paste onto pads by hand since there's no stencil — this is the
  part that needs the most care at 0402 size
- Fine-tip soldering iron for touch-up/rework and for the through-hole
  pogo-pin/spring contact if it isn't reflowed
- Kapton tape or similar heat-safe tape to hold the board flat/in place
  on the hot plate
- Flux pen + isopropyl alcohol for cleanup after soldering
- Fine ESD tweezers and a magnifier/loupe or microscope — needed for
  placing 0402 passives and 0603 LEDs, and for nudging the BQ25185 into
  place on its 0.4mm-pitch pads
- Multimeter, for continuity/short checks before power-up, especially
  since the board edge is copper-plated and acts as the ground/negative
  contact against the flashlight case — an accidental bridge here is a
  direct short across the cell
- USB-C power source (a basic 5V source is enough, no PD negotiation
  needed) to test charging once assembled
- Bench power supply / current-limited source recommended for first
  power-up, to catch a bad solder joint before it takes the cell with it

## Case & mechanical fit

The case mod and pogo-pin connector are custom FreeCAD parts
(`case/Case.FCStd`, `pcb/PogoPinConnector/`), fitted into the D4v2's
body/head threaded joint (`case/Thread_tests/ThreadTester.FCStd`):

- Means to cut/print the modified body threads to match the D4v2's
  joint — a tap matching the body's thread pitch if machining an
  existing aluminum body, or a 3D printer/CNC if producing a test or
  replacement part. Print/machine and check fit with the thread tester
  model before committing to the real body.
- Calipers, to confirm the sandwiched board's thickness and the pogo-pin
  standoff height fit the joint gap before final assembly
- Small pin press or arbor press, for seating the pogo pins into the
  connector housing without bending them
- Drill/reamer sized to the pogo-pin housing bore, if machining the body
  directly rather than printing a new part

## Final assembly

- No tools needed to reassemble the body/head — it's a hand-tightened
  threaded joint
- Isopropyl alcohol and lint-free wipes for a final clean before closing
  everything up (flux residue near the cell contact is worth avoiding)
