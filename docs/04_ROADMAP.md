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
Compare:
- conventional 65%
- unibody semi-split
- moderate column stagger
- thumb cluster options

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

### 4. Mode selector
Compare slider, rotary and other mechanisms.

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

The display must complement, not replace, the physical mode selector.

### 6. CAD tooling
Compare open-source-capable CAD workflows.

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
- mode input

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
- mode selector integration
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
- physical context selector
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
