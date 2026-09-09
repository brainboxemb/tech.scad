# User projects

This index contains concrete CAD projects in the wider SCAD landscape.

A repository is not classified as a SCAD project merely because its name
contains `.cad.`. The repository contents are checked for actual OpenSCAD or
PythonSCAD use.

For OpenSCAD, real `.scad` source files are direct evidence. For PythonSCAD,
a generic `.py` file is not enough: project configuration, PythonSCAD-specific
source/API use or build invocation should provide the evidence.

## Current projects

| Repository | Engine | Infrastructure | Purpose |
| --- | --- | --- | --- |
| [`2026-009-01.cad.HUB75-display-frame`](https://github.com/brainboxemb/2026-009-01.cad.HUB75-display-frame) | OpenSCAD | current / `tool.scad-project` | Structured restart of the five-panel HUB75 display frame using reusable `lib.scad.hub75` panel geometry. |
| [`2026-003-01.cad.garden-tool-cart`](https://github.com/brainboxemb/2026-003-01.cad.garden-tool-cart) | OpenSCAD | classic / `brainboxemb.github.actions` | Modular storage solutions for a mobile garden tool rack. |
| [`2026-004-01.cad.metabo-tsu-slot-insert`](https://github.com/brainboxemb/2026-004-01.cad.metabo-tsu-slot-insert) | OpenSCAD | classic / standalone | Insert that locates mounting bolts in a Metabo TSU table-saw stand. |
| [`2026-005-01.cad.aluminium-profile-mft`](https://github.com/brainboxemb/2026-005-01.cad.aluminium-profile-mft) | OpenSCAD | classic / standalone | Aluminium-extrusion MFT-style multifunction workbench. |
| [`2026-006-01.cad.HUB75-display-frame`](https://github.com/brainboxemb/2026-006-01.cad.HUB75-display-frame) | OpenSCAD | classic / `brainboxemb.github.actions` | Mechanical frame for HUB75 LED matrix panels. |
| [`2026-006-02.cad.HUB75-display-case`](https://github.com/brainboxemb/2026-006-02.cad.HUB75-display-case) | OpenSCAD | classic / `brainboxemb.github.actions` | Wooden enclosure and carry structure for a HUB75 LED display. |
| [`2026-007-01.cad.tool-board`](https://github.com/brainboxemb/2026-007-01.cad.tool-board) | OpenSCAD | classic / `brainboxemb.github.actions` | Parametric garage/workshop layout and tool-board planning model. |
| [`2026-008-01.cad.bosch-table`](https://github.com/brainboxemb/2026-008-01.cad.bosch-table) | OpenSCAD | classic / `brainboxemb.github.actions` | Mobile workshop stand for the Bosch GTS 10 XC table saw. |

The catalog now contains seven classic CAD projects plus the new current-generation HUB75 frame project. All listed user CAD repositories contain OpenSCAD source; none currently contains detected PythonSCAD project source.

New projects are expected to use the current `tool.scad-project` /
`docker.scad-toolchain` infrastructure. Existing classic projects do not need
to be reclassified merely because a newer infrastructure exists.

## Project ownership

The project repository remains the source of truth for dimensions, design
status, source files, build output and project-specific documentation.

The canonical machine-readable membership and classification list is
[`../catalog.yml`](../catalog.yml).
