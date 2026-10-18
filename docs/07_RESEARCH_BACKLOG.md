# DVN Research Backlog

This file contains unresolved questions that should be investigated before they become design decisions.

Priority can change as dependencies become clearer.

---

# HIGH PRIORITY

## 1. Keyboard geometry / mechanical validity (CURRENT BLOCKER)
**Selected allocation:** B3 expanded-navigation, straight rectangular ISO-ES, physical arrow cluster, **2u Backspace** and **5.75u Space**, with `º/ª` removed from physical top row in favor of proposed Fn access.

**Next experiments / open questions:**
- update FreeCAD master from older 15.75u to B3 **17u** and confirm nominal full key allocation / switch count
- compute exact switch centers and validate every 14 mm nominal MX cutout and all keycap clearances, including ISO Enter
- verify location, orientation and supported footprints for ISO Enter and stabilizers
- source or validate **5.75u** Space keycap and corresponding stab scheme; propose alternate if unavailable
- validate Fn+Esc / Fn+Shift+Esc `º/ª` on QMK and with actual ISO-ES OS keyboard configuration
- 1:1 physical testing: reach, typing comfort, wrist/forearm posture, navigation usability and portability
- no extra protrusions on final rectangle; quantify display/encoder area without overlaps or excessive blank housing
- coordinate FreeCAD plate/case geometry with KiCad MX 5-pin hot-swap sockets and PCB mounts

Previous G1R+ semi-split and B1/B2 variants remain useful historic comparisons, not the current selected layout.

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

## 4. Context control / push rotary encoder UX
The dedicated physical mode selector has been removed from the Rev 1 direction. Context selection and local device navigation will use the Context Display + push rotary encoder.

Research:
- encoder detent feel and resolution
- push force and durability
- rotate / press navigation model
- short-press vs long-press behavior
- accidental activation prevention
- menu depth and discoverability
- rapid access to context, volume and lighting controls
- firmware state model and feedback timing
- accessibility and use without resident PC software

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
the display must make the active context clear and provide immediate feedback for encoder navigation and adjustments.

## 6. CAD workflow (TOOL SELECTED; PIPELINE NOT YET VALIDATED)
**FreeCAD 1.1.4** is selected as the primary mechanical tool and **KiCad** for PCB. The local `DVN65_MasterLayout.FCStd` has Spreadsheet parameters, a 15.75u reference construction sketch and a hidden 15-center test row; these artifacts are not yet committed to GitHub.

Validate:
- reproducible parametric full-layout generation and collision reports
- sharing origins/units with KiCad footprints and checking stab/socket clearances
- FreeCAD and KiCad exports (STEP/DXF/board outline) plus rebuild instructions
- archived source CAD/macro versions in repository after validation

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
- push-encoder I/O impact
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

## 12. Mechanical mounting / premium balanced acoustics
**Current experiment:** gasket mount with controlled compression to target firm but comfortable feel and deep, defined office-appropriate sound. Compare against simpler mounting when geometry stabilizes. Validate tactile response, screw/fastener accessibility, gasket compression, serviceability and unit cost.

## 13. Plate materials and damping
**Prototype baseline:** FR4 approximately 1.5 mm, interchangeable aluminium alternative. Check 14 × 14 mm nominal MX openings, switch retention, FR4 fabrication tolerances, gasket interfaces, and optional/removable PORON/EVA damping. Validate sound with foam installed and removed.

## 14. Case material / screen and encoder
CNC aluminium is a provisional premium candidate. Balance weight, CNC cost, durability, acoustic behavior and portability. Determine a single clean rectangular case silhouette, right-hand display/encoder reserve and rigid control mounting isolated from a gasket-suspended plate if needed.

## 15. Stabilizers and non-standard keycaps
High-priority gate before plate/PCB: verify the exact **5.75u** spacebar keycap supply and compatible stabilizer spacing. Also confirm ISO Enter, 2u Backspace, Shift and any larger navigation modifiers; PCB screw-in stabilizer mechanical compatibility and socket/diode/trace interference.

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
