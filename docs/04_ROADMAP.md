# DVN Roadmap

## Current phase
**Phase 1 — Research**

## Current objective
Validate the highest-impact product assumptions with evidence before committing to PCB or mechanical architecture. Geometry and ergonomics are the first research track.

---

## Phase 0 — Foundation
**Status:** COMPLETE — 2026-09-23

### Goals
- project instructions
- project source files
- product vision
- product specification
- architecture overview
- decision tracking
- engineering log
- research backlog

### Exit criteria
The project has a clear source of truth and unresolved questions are explicitly identified.

**Exit result:** Met. Core documentation, repository structure, source-of-truth rules, decision tracking, engineering log and research backlog are established.

---

## Phase 1 — Research

### 1. Ergonomics and geometry
**Current Phase 1 progress (2026-10-18):**
- Historical semi-split/G1R+ and 65% experiments retained; **B3 expanded-navigation rectangular ISO-ES** selected as working key-layout baseline.
- Nominal width **17u** at **19.05 mm** pitch; Backspace **2u**; Space **5.75u**; inverted-T physical arrows; expanded right navigation; `º/ª` moved to provisional Fn combinations.
- Selection was made from visual comparisons; it is **not a physically validated manufacturing layout**.

**Next validation gate before PCB/plate:**
1. update FreeCAD master from former 15.75u reference to approved 17u B3
2. generate the complete switch-center geometry and independently check for overlapping key/switch footprints and impossible cutouts
3. verify ISO Enter switch position, stab supports, 5.75u spacebar keycap and suitable stabilizer compatibility
4. test 1:1 physical mockup for reach, key-spacing and actual typing posture
5. define right-side display/encoder clearance inside one clean external rectangle; keep these controls mechanically separate from any suspended plate as needed
6. document final accepted key count and key-to-electrical-matrix mapping

### 2. Developer Layout
Analyze real code from:
- C#/.NET
- SQL
- JavaScript/TypeScript
- Python
- HTML/CSS

Measure:
- character frequency
- symbol frequency
- modifier use
- pinky load
- travel distance
- common pairs/sequences

### 3. Adaptive Legends research
Investigate:
- LED wavelengths
- optical filters
- PET films
- masks
- diffusion
- relegendable keycaps
- ambient-light readability

### 4. Context control / push rotary encoder
Prototype the on-device control model using the Context Display and a push rotary encoder.

Evaluate:
- encoder detent feel and resolution
- push force
- rotate / press navigation
- short-press vs long-press behavior
- context selection speed
- volume / lighting adjustment
- accidental activation prevention
- menu depth and discoverability

### 5. DVN Context Display
Research the minimum integrated display suitable for Rev 1.

Compare:
- monochrome OLED
- color IPS/TFT
- I²C vs SPI
- main-PCB vs daughterboard integration
- memory / flash / GPIO requirements
- power
- mechanical integration
- UI constraints
- cost

The display must clearly communicate active context and provide immediate feedback for encoder navigation and adjustments.

### 6. CAD tooling
**FreeCAD 1.1.4 selected** as mechanical CAD master; **KiCad selected** for custom PCB. Local working file `hardware/mechanical/freecad/DVN65_MasterLayout.FCStd` uses a Spreadsheet, fully constrained reference sketch and a hidden test row of 15 switch centers. It has not yet been added to GitHub.

Remaining: reproducible FreeCAD generator/macro, source CAD committed to repository, stabilizer and hot-swap footprint alignment, manufacturing exports, FreeCAD ↔ KiCad coordinate conventions.

### 7. Premium mechanical/acoustic proof direction
Chosen user target: **Premium equilibrado**, firm but comfortable, controlled deep and defined sound. Trial hypothesis: gasket mounting, 1.5 mm FR4 plate, aluminium alternative and modular removable PORON/EVA damping. Confirm by prototyping before finalizing mounting, material or case.


---

## Phase 2 — Adaptive Legends Proof of Concept
Build a one-key experiment.

Initial pair:
`U ↔ {`

Success criteria:
- alternate legend is clearly visible in CODE state
- result works under normal room/office lighting
- crosstalk is acceptable
- prototype cost is low enough to iterate

---

## Phase 3 — Electronic Devboard
Build a small electronics prototype with:
- MCU candidate
- several switches
- diodes
- RGB/optical LED
- encoder
- small display candidate
- USB
- push rotary encoder

Goal:
prove core firmware behavior before designing the full keyboard PCB.

---

## Phase 4 — DVN Protocol + DVN Studio MVP
Minimum working path:

```text
DVN Studio
   ↓
USB
   ↓
Firmware
   ↓
read/write configuration
```

MVP capabilities:
- detect device
- read device information
- remap one key
- change one mode setting
- control one LED/legend
- save configuration persistently

---

## Phase 5 — PCB Rev 0
Create first full keyboard PCB.

Activities:
- schematic
- ERC
- footprints
- PCB layout
- DRC
- fabrication outputs
- BOM
- assembly plan

Rev 0 may be development-oriented rather than final-size production hardware.

---

## Phase 6 — Mechanical Prototype
Design:
- case
- plate
- mounting
- control-island integration
- encoder integration
- Context Display integration/window
- module attachment geometry

Use affordable external prototype manufacturing.

---

## Phase 7 — Module Prototype
First module:
- 3–6 macro keys
- encoder

Validate:
- mechanical attachment
- pogo pins
- communication
- discovery
- configuration
- DVN Studio integration

---

## Phase 8 — Integrated Prototype
Combine:
- full keyboard PCB
- mechanical enclosure
- Developer Layout
- Context System
- Context Display
- Adaptive Legends
- module interface
- firmware
- DVN Studio

Perform real daily-use testing.

---

## Phase 9 — DVN-65 Rev 1.0
Target first complete version.

Success criteria:
- custom PCB
- custom case/plate
- ISO-ES usable layout
- hot-swap MX 5-pin
- USB-C
- WRITE/CODE/DEV/GAME/CUSTOM
- push rotary encoder context control
- functional Adaptive Legends
- Action Key
- contextual encoder
- small contextual display for mode/status/encoder feedback
- persistent configuration
- DVN Studio
- at least one functional module
- reproducible documentation
- BOM and manufacturing files
- cost reasonably close to target
- suitable for daily programming and office transport
