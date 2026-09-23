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

## DVN Context Display
Rev 1 should include a small integrated contextual display near the encoder/control area.

Its minimum role is to show active context and temporary encoder/status feedback. It may also show profile information and simple user-configurable icons or a lightweight mascot.

The display and push rotary encoder together form the primary on-device context-control interface.

## Context control interface
Rev 1 will not use a separate physical mode selector.

WRITE / CODE / DEV / GAME / CUSTOM selection, on-device menu navigation and adjustable controls will be integrated through the Context Display and a push rotary encoder. The display provides the visual state; encoder rotation navigates or changes values; encoder press selects/confirms or enters the interface.

Exact menu shortcuts and short-press / long-press behavior remain to be validated.

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

## G1R+ v5 geometry candidate
Current Phase 1 working candidate for physical validation.

Direction:
- approximately 65% ISO-ES
- unibody semi-split
- 6° per half / 12° total opening
- conventional row stagger
- split space with both halves acting as Space during geometry testing
- physical arrow cluster retained
- dedicated Del / PgUp / PgDn / Home / End removed in favor of Fn-layer access
- Context Display at the upper edge of the right control area
- push rotary encoder below the display

This is an **experimental geometry candidate**, not the final geometry decision. It must be validated with 1:1 physical testing before PCB/mechanical commitment.

## Thumb cluster
May replace or divide parts of a traditional long spacebar if it improves ergonomics without imposing a large learning curve.

---

# TBD — RESEARCH REQUIRED

## Final geometry
Conventional 65% vs unibody semi-split vs moderate stagger.

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

## DVN Context Display implementation
Research required for:
- monochrome OLED vs color IPS/TFT
- physical size and resolution
- I²C vs SPI
- framebuffer/RAM/flash requirements
- power consumption
- QMK/firmware rendering approach
- main-PCB vs daughterboard implementation
- mechanical window/protection
- user-configurable asset limits
- unit-cost impact

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

## Dedicated physical context selector
Reason:
A separate slider or selector duplicates functionality that can be provided by the Context Display + push rotary encoder interface while consuming valuable top-surface area.

Rev 1 will use the encoder/display interface instead.

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
- larger/secondary display module
- trackball/touchpad module
- carry case
- small-batch production
- group buy
- crowdfunding
