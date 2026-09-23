# DVN Design Decisions

This file tracks current design state.

## Status definitions
- **DECIDED** — approved and currently authoritative
- **TBD — Research Required** — requires investigation
- **EXPERIMENTAL** — hypothesis requiring prototype/test
- **REJECTED** — intentionally not chosen
- **FUTURE** — possible later revision

---

# DECIDED

## Project identity
**DVN — Dynamic Visual Nexus**

First product: **DVN-65**

## Primary purpose
Portable, premium, modular keyboard optimized for software development.

## Learning philosophy
The project should maximize useful learning and hands-on engineering rather than simply minimize development time.

## Layout preference
ISO-ES with familiar letter positions and a conventional overall typing experience.

## General form factor
Approximately 65%, while allowing research into moderate ergonomic geometry.

## Switch standard
MX compatible, 5-pin.

## Hot-swap
Mandatory.

## Connectivity
USB-C wired for Rev 1.

## Resident software
Not required for normal operation.

Configuration must persist on the keyboard.

## Programming priority
1. C#/.NET
2. SQL
3. JavaScript/TypeScript
4. Python
5. HTML/CSS

## Context modes
- WRITE
- CODE
- DEV
- GAME
- CUSTOM

## CODE vs DEV
CODE focuses on symbols, navigation and code entry.

DEV focuses on tools such as build, run, debug, terminal, Git and IDE actions.

## Lighting philosophy
Primarily functional, not gaming-oriented.

## Action Key
Provider-independent and user configurable.

## Firmware direction
QMK as base, with DVN-specific extensions.

## Software direction
C#/.NET with Avalonia as preferred UI technology.

## Operating system priority
Windows first, while avoiding unnecessary barriers to macOS/Linux.

## PCB design
Custom PCB using KiCad.

## Modular direction
Open module system with side attachment.

## Initial module
3–6 macro keys + encoder.

## Module mechanical direction
Magnets + alignment guides + pogo pins.

## Public development
Repository/project developed publicly from the beginning.

## GitHub write policy
No repository modifications without explicit confirmation from David.

## Final product cost
Target ≤ €200, soft maximum €250.

## R&D budget
Approximately €300.

## Manufacturing constraint
No personal 3D printer; use external prototype/manufacturing services.

## Acoustic target
Premium, controlled, deep and office-appropriate.

---

# EXPERIMENTAL

## DVN Adaptive Legends
Use optical filtering/illumination so alternate functions become visually apparent when the context changes.

The original legend may remain visible; the secondary legend must clearly appear.

## Unibody semi-split / moderate column stagger
Potential ergonomic direction if benefits justify the additional complexity.

## Thumb cluster
May replace or divide parts of a traditional long spacebar if it improves ergonomics without imposing a large learning curve.

---

# TBD — RESEARCH REQUIRED

## Final geometry
Conventional 65% vs unibody semi-split vs moderate stagger.

## Mode selector
Slider, rotary selector or another mechanism.

## MCU
Must be selected after real I/O and memory requirements are known.

## Matrix architecture
Rows/columns and scanning details.

## Adaptive Legends optical implementation
- LED wavelengths
- filter materials
- PET/masks
- diffusion
- keycap structure

## Functional lighting colors
Must account for optical filtering requirements.

## Module communication bus
Candidates may include I²C, UART, USB or another protocol.

## Hot-plug behavior
Need electrical and firmware safety analysis.

## DVN Protocol transport
Potentially USB HID / Raw HID.

## CAD software
Prefer open-source when viable.

## Mounting system
TBD.

## Plate material
TBD.

## Case material
TBD.

## Stabilizers
TBD.

## Final switches
TBD.

## Open-hardware license
Candidate: CERN-OHL-W-2.0.
Needs dedicated license review.

---

# REJECTED / NOT REV 1

## Wireless connectivity in Rev 1
Reason:
Adds RF, battery, charging and firmware complexity before core DVN concepts are validated.

May be reconsidered in a future revision.

## Provider-specific AI key
Reason:
Would tie hardware to a particular service or brand.

Use configurable DVN Action Key instead.

---

# FUTURE

Possible later areas:
- wireless revision
- additional modules
- numpad module
- navigation module
- display module
- trackball/touchpad module
- carry case
- small-batch production
- group buy
- crowdfunding
