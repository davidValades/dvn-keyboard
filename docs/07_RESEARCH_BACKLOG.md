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

## 5. CAD tool
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

## 6. MCU selection
Do not choose until requirements are estimated.

Compare:
- GPIO
- USB support
- RAM
- flash
- persistent storage options
- QMK support
- availability
- package/solderability
- price
- documentation
- power consumption

RP2040 is a candidate, not a decision.

## 7. Key matrix
Determine:
- likely key count
- rows/columns
- GPIO requirements
- diode orientation
- module/mode/encoder I/O impact

## 8. DVN Module Bus
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

## 9. Module hot-plug safety
Research:
- power sequencing
- ESD
- contact bounce
- data-line protection
- firmware detection
- pogo-pin insertion behavior

## 10. DVN Studio protocol
Research:
- QMK Raw HID
- HID reports
- versioning
- configuration serialization
- backward compatibility

---

# LATER

## 11. Mechanical mounting system
Compare:
- gasket
- top mount
- tray
- O-ring
- other approaches

Do not prioritize until geometry is more stable.

## 12. Plate materials
Compare:
- FR4
- aluminium
- polycarbonate
- POM
- steel
- others

## 13. Case material
Balance:
- premium feel
- weight
- CNC cost
- durability
- acoustic behavior
- transportability

## 14. Stabilizers
Evaluate after layout and PCB geometry stabilize.

## 15. Switch selection
Final switch is not required to design the platform.

Target office-appropriate acoustics.

## 16. Carry case
Design only after external dimensions and module strategy stabilize.

## 17. Commercialization
Later research:
- group buy
- crowdfunding
- small-batch production
- CE/EMC implications
- packaging
- logistics
- warranty
- production BOM

## 18. Open-hardware licensing
Review:
- CERN-OHL-W-2.0
- alternatives
- interaction with firmware/software licenses
