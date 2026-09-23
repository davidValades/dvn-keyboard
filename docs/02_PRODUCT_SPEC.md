# DVN-65 Product Specification

**Status:** Living specification  
**Product:** DVN-65  
**Platform:** DVN — Dynamic Visual Nexus

## 1. Product category
Portable premium modular mechanical keyboard optimized for software development.

## 2. Target cost
- Target final unit cost: **≤ €200**
- Soft maximum: **€250**
- Approximate total R&D budget: **€300**
- Personal design/assembly labor cost: **€0** for personal cost calculations

Prefer inexpensive validation experiments before expensive fabrication.

## 3. Form factor
Initial direction: approximately **65%**.

Final geometry is not decided.

Must research:
- conventional 65%
- unibody semi-split
- moderate column stagger
- subtle ergonomic angle

Constraint: retain a familiar typing experience.

## 4. Layout
Preferred primary layout: **ISO-ES**

Must preserve:
- Ñ
- ISO Enter
- conventional letter positions
- familiar general typing behavior

Moderate changes may be explored for:
- thumb cluster
- auxiliary keys
- mode controls
- symbol access
- modules

## 5. Switch compatibility
Required:
- MX compatible
- 5-pin support
- hot-swap

## 6. Connectivity
Rev 1:
- USB-C wired

Not planned for Rev 1 unless requirements change:
- Bluetooth
- 2.4 GHz
- battery

## 7. Standalone operation
DVN Studio must not be required during normal use.

Configuration must persist on-device so the keyboard can be configured at home and used on another PC without installing resident software.

## 8. Programming priorities
Developer-layout research priority:
1. C# / .NET
2. SQL
3. JavaScript / TypeScript
4. Python
5. HTML / CSS

Research should analyze:
- symbol frequency
- modifier usage
- pinky load
- travel distance
- common pairs/sequences
- hand alternation

Important symbols include:
`{} [] () <> ; : = + - _ / \ | & ! ? # @ ' " ` ~ . ,`

## 9. Modes

### WRITE
General typing and navigation.

### CODE
Direct and ergonomic access to programming symbols and code navigation.

### DEV
Development-environment actions such as:
- build
- run
- debug
- stop
- step over
- step into
- terminal
- Git
- command palette
- IDE actions

### GAME
Gaming-oriented profile.

### CUSTOM
Fully user-configurable through DVN Studio.

## 10. Physical mode selector
A physical context selector is required.

Candidate mechanisms:
- multi-position slider
- rotary selector
- mechanical switch
- other tactile mechanism

**Status:** TBD — Research Required

The current mode should ideally be identifiable physically without depending only on software.

## 11. Encoder
A contextual rotary encoder is planned.

Possible behavior:
- WRITE: scroll/media
- CODE: editor zoom/tab navigation
- DEV: errors/debug navigation
- GAME: volume
- CUSTOM: user-defined

Encoder press may provide an additional action.

## 12. DVN Context Display
A small integrated contextual display is planned for Rev 1, positioned near the encoder/control area.

Primary purposes:
- show the active context: WRITE / CODE / DEV / GAME / CUSTOM
- show temporary encoder function or feedback
- show profile or device status
- show simple user-configurable icons or a lightweight mascot/visual

The display must complement, not replace, the physical mode selector. The active context should still be physically understandable without depending only on the display.

Candidate technologies:
- small monochrome OLED
- small color IPS/TFT
- other compact display technologies if justified

Candidate interfaces:
- I²C
- SPI

Constraints:
- low physical footprint
- low power consumption
- limited MCU/RAM/flash impact
- reasonable cost
- readable viewing angle
- mechanically protectable
- no resident PC software required during normal use

The display may be implemented directly on the main PCB or through a small daughterboard if that reduces prototype or revision risk.

**Presence in Rev 1:** DECIDED  
**Technology / size / interface / UI implementation:** TBD — Research Required

## 13. DVN Action Key
A configurable physical key independent of any specific provider.

May trigger:
- AI assistant
- IDE assistant
- application
- terminal
- macro
- shortcut
- script
- command palette

Its function may vary by mode.

## 14. Adaptive Legends
A core experimental feature.

Goal: alternate functions should become visibly apparent through controlled illumination and optical filtering.

Example:
- WRITE: `U`
- CODE: alternate `{` function becomes clearly visible

The original legend may remain visible. Full disappearance is not required.

Technology is not finalized.

**Status:** EXPERIMENTAL

## 15. Lighting
RGB/lighting should be primarily functional.

Possible semantic uses:
- normal typing
- navigation
- code symbols
- debug/run
- AI/action functions
- module state

Exact colors remain TBD because optical filtering requirements may constrain them.

## 16. Modular system
The keyboard should support side modules.

Preferred conceptual direction:
- magnetic retention
- mechanical alignment guides
- pogo pins
- automatic identification

The interface should eventually be documented as an open standard.

## 17. First module
Initial module target:
- 3–6 macro keys
- rotary encoder

Purpose: validate mechanical attachment, electrical connection, protocol, firmware and DVN Studio integration.

## 18. Firmware
Preferred base: **QMK**

DVN-specific firmware should implement:
- modes
- module support
- configuration protocol
- Adaptive Legends behavior
- Context Display state/feedback
- persistent profiles/settings

## 19. Software
Preferred stack:
- C#
- .NET
- Avalonia

Priority platform:
- Windows

Architecture should avoid unnecessary barriers to future:
- macOS
- Linux

Target features:
- device detection
- keymap configuration
- layers
- modes
- CUSTOM mode
- macros
- profiles
- module configuration
- encoder configuration
- Context Display behavior and simple user visuals
- lighting
- Action Key
- import/export
- diagnostics
- firmware/device information
- update support when appropriate

## 20. Mechanical goals
- premium feel
- portable
- office-appropriate
- minimal/professional aesthetic
- durable
- repairable

Final materials are TBD.

## 21. Acoustic goal
Premium, controlled and deep, but appropriate for office use.

Avoid:
- excessive loudness
- metallic resonance
- gaming-oriented sound gimmicks

## 22. CAD
Prefer open-source tools when viable.

Candidates to research:
- FreeCAD
- SolveSpace
- OpenSCAD
- others

**Status:** TBD — Research Required

## 23. Manufacturing
David does not own a 3D printer.

Design prototypes around affordable external services:
- PCB manufacturing
- 3D printing
- resin
- CNC
- laser cutting
- PET printing
- graphic/optical fabrication

## 24. Open hardware
Desired philosophy:
- public
- understandable
- modifiable
- reproducible
- potentially commercially usable

Candidate license:
- CERN-OHL-W-2.0

**Status:** TBD — License Review Required
