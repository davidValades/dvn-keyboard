# DVN Research Backlog

This file contains unresolved questions that should be investigated before they become design decisions.

Priority can change as dependencies become clearer.

---

# HIGH PRIORITY

## 1. Keyboard geometry
Compare:
- conventional 65%
- unibody semi-split
- subtle column stagger
- split-space/thumb-cluster variants

Questions:
- measurable ergonomic benefit?
- learning cost?
- ISO-ES compatibility?
- portability impact?
- CAD/PCB complexity?
- keycap availability?

## 2. Developer Layout
Build a dataset of real code from:
- C#/.NET
- SQL
- JavaScript/TypeScript
- Python
- HTML/CSS

Measure:
- symbol frequency
- character pairs
- modifier frequency
- pinky load
- travel distance
- hand alternation
- repeated actions

Goal:
design a CODE layout using data rather than intuition.

## 3. Adaptive Legends optical proof of concept
Initial experiment:
`U ↔ {`

Research:
- RGB LED wavelength characteristics
- red/green/blue filter combinations
- PET films
- print processes
- masks
- diffusion
- relegendable MX keycaps
- ambient-light performance
- crosstalk

Success criteria must be defined before testing.

## 4. Physical context selector
Compare:
- slider
- rotary selector
- multi-position switch
- alternative tactile mechanisms

Evaluate:
- tactile clarity
- physical state visibility
- durability
- size
- availability
- cost
- electrical complexity
- CAD integration

## 5. DVN Context Display
The display itself is part of the Rev 1 direction; implementation is not decided.

Compare:
- monochrome OLED
- color IPS/TFT
- other compact display technologies if justified
- I²C
- SPI
- main-PCB integration
- daughterboard integration

Determine:
- minimum useful physical size
- resolution and viewing-angle requirements
- RAM/framebuffer requirements
- flash requirements for fonts/icons/simple mascots
- GPIO/interface requirements
- refresh-rate needs
- power consumption
- QMK compatibility and rendering strategy
- encoder-feedback behavior
- mode/status UI behavior
- user-configurable asset limits
- mechanical window/protection
- assembly complexity
- unit-cost impact

Constraint:
the display must complement, not replace, the physical context selector.

## 6. CAD tool
Compare open-source-friendly tools for:
- parametric modeling
- assemblies
- STEP
- DXF
- keyboard case design
- CNC
- 3D-print prototypes

Candidate tools:
- FreeCAD
- SolveSpace
- OpenSCAD
- others

---

# MEDIUM PRIORITY

## 7. MCU selection
Do not choose until requirements are estimated.

Compare:
- GPIO
- USB support
- RAM
- flash
- persistent storage options
- display/framebuffer requirements
- QMK support
- display-library/support implications
- availability
- package/solderability
- price
- documentation
- power consumption

RP2040 is a candidate, not a decision.

## 8. Key matrix and I/O budget
Determine:
- likely key count
- rows/columns
- GPIO requirements
- diode orientation
- module I/O impact
- mode-selector I/O impact
- encoder I/O impact
- Context Display interface impact

## 9. DVN Module Bus
Compare:
- I²C
- UART
- USB
- CAN-like approaches if justified
- other options

Requirements:
- module identification
- low pin count
- reliable pogo-pin connection
- possible hot-plug behavior
- future extensibility
- low cost

## 10. Module hot-plug safety
Research:
- power sequencing
- ESD
- contact bounce
- data-line protection
- firmware detection
- pogo-pin insertion behavior

## 11. DVN Studio protocol
Research:
- QMK Raw HID
- HID reports
- versioning
- configuration serialization
- backward compatibility
- Context Display configuration and simple asset transfer if required

---

# LATER

## 12. Mechanical mounting system
Compare:
- gasket
- top mount
- tray
- O-ring
- other approaches

Do not prioritize until geometry is more stable.

## 13. Plate materials
Compare:
- FR4
- aluminium
- polycarbonate
- POM
- steel
- others

## 14. Case material
Balance:
- premium feel
- weight
- CNC cost
- durability
- acoustic behavior
- transportability

## 15. Stabilizers
Evaluate after layout and PCB geometry stabilize.

## 16. Switch selection
Final switch is not required to design the platform.

Target office-appropriate acoustics.

## 17. Carry case
Design only after external dimensions and module strategy stabilize.

## 18. Commercialization
Later research:
- group buy
- crowdfunding
- small-batch production
- CE/EMC implications
- packaging
- logistics
- warranty
- production BOM

## 19. Open-hardware licensing
Review:
- CERN-OHL-W-2.0
- alternatives
- interaction with firmware/software licenses
