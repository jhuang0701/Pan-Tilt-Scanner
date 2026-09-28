# Pan-Tilt Scanner Controller

A two-axis pan/tilt scanner controller designed in KiCad. The project includes the schematic, PCB, a schematic PDF export, a grouped bill of materials, and fabrication outputs. The supplied project files show two Pololu A4988 stepper-driver carrier modules controlled by an STM32F103C8Tx.

## What it does

The board provides control and power circuitry for two stepper-driven axes. An STM32F103C8Tx microcontroller interfaces with two Pololu A4988 carrier modules. An LM2596S-5 switching regulator and an AP2112K-3.3 linear regulator provide the board's 5 V and 3.3 V rails.

## Core components

- **Microcontroller:** STM32F103C8Tx (U3), the board's central controller.
- **Stepper drivers:** Two Pololu A4988 carrier modules (A2 and A3), for the two motion axes.
- **5 V regulator:** LM2596S-5 (U1), a switching regulator.
- **3.3 V regulator:** AP2112K-3.3 (U2), a linear regulator.
- **Clock:** Crystal Y1 with two 20 pF capacitors.

## Design decisions worth knowing about

- The design uses two Pololu A4988 carrier modules rather than placing the stepper-driver ICs directly on the PCB.
- The power section provides 5 V and 3.3 V regulated rails using separate switching and linear regulator devices.
- The PCB stackup defines front and back copper layers and a nominal total board thickness of 1.6 mm.

## Specs

| Specification | Verified value |
| --- | --- |
| Stepper-driver interfaces | 2 x Pololu A4988 carrier modules |
| Regulated rails | +5 V, +3.3 V |
| Copper layers | 2 |
| Board thickness | 1.6 mm |

## Repo contents

- [`schematic/`](schematic/) - KiCad schematic, PCB, project settings, and one-page schematic PDF export.
- [`gerbers/`](gerbers/) - Gerber layers, plated and non-plated drill files, Gerber job file, and the supplied ZIP bundle. The ZIP contains byte-identical copies of the individual Gerber and drill files.
- [`bom/`](bom/) - Grouped bill of materials CSV.
- [`public/`](public/) - Presentation screenshots: [3D board view, angle 1](public/pan-tilt-scanner-3d-angle-1.png), [3D board view, angle 2](public/pan-tilt-scanner-3d-angle-2.png), and [2D PCB layout](public/pan-tilt-scanner-pcb-2d-layout.png).

The root-level [pan_tilt_scanner-all-pos.csv](pan_tilt_scanner-all-pos.csv) is a component placement export, not a bill of materials. No separate render assets were present, so there is no `render/` folder.

## Status

The KiCad schematic and PCB files, a schematic PDF, and fabrication exports are present. DRC status has not been verified, and the repository contains no confirmation of fabrication or assembly.
