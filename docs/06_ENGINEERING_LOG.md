# DVN Engineering Log

Chronological engineering journal.

Do not remove failed experiments. Negative results are valuable project knowledge.

---

## Entry template

### YYYY-MM-DD — Experiment / Work Item

**Area:**  
Optics / electronics / firmware / mechanical / software / ergonomics / manufacturing / other

**Objective:**  
What are we trying to learn or validate?

**Hypothesis:**  
What do we expect to happen?

**Setup / Materials:**  
List relevant components, tools, files, versions and conditions.

**Procedure:**  
What was done?

**Measurements / Evidence:**  
Record quantitative measurements where possible.

**Result:**  
What happened?

**Problems:**  
Unexpected behavior, failures, limitations.

**Conclusion:**  
What did we learn?

**Decision impact:**  
Does this change any design decision?

**Next step:**  
What should be tested or built next?

**References / files:**  
Links, photos, commits, datasheets, CAD/PCB files, etc.

---

# Log

## 2026-09-23 — Project definition baseline

**Area:** Project architecture

**Objective:**  
Define the initial identity and engineering direction for DVN.

**Result:**  
The project was defined as a portable, premium, modular developer keyboard platform named **DVN — Dynamic Visual Nexus**, with the first keyboard provisionally called **DVN-65**.

Core differentiators:
- Context System
- Adaptive Legends
- Developer Layout
- Module Interface
- DVN Studio
- Action Key

Major constraints established:
- ISO-ES preferred
- approximately 65%
- familiar typing experience
- USB-C wired
- MX 5-pin hot-swap
- standalone operation
- QMK base firmware
- C#/.NET/Avalonia software direction
- target unit cost ≤ €200
- public/open development

**Conclusion:**  
The concept is sufficiently defined to begin structured research before PCB design.

**Next step:**  
Complete Phase 0 documentation and begin Phase 1 research.


---

## 2026-09-23 — Phase 0 completion and Context Display baseline

**Area:** Project architecture / product definition

**Objective:**  
Close the foundation phase, align the public repository with the project source of truth, and incorporate the small contextual display introduced during concept development.

**Result:**  
Phase 0 documentation is now represented in the public repository under `docs/`, with the README acting as presentation/navigation rather than a competing specification.

A small integrated display was added to the Rev 1 product direction as **DVN Context Display**.

Baseline display intent:
- located near the encoder/control area
- show WRITE / CODE / DEV / GAME / CUSTOM context
- provide temporary encoder/action feedback
- show profile or device status
- optionally show a simple user-configurable icon or lightweight mascot
- remain useful without resident software after configuration
- complement rather than replace the physical context selector

The exact display technology, size, interface, memory requirements, mechanical implementation and cost are intentionally unresolved.

Phase 0 exit criteria are considered satisfied.

**Decision impact:**  
- DVN Context Display presence becomes part of the Rev 1 direction.
- Display implementation remains **TBD — Research Required**.
- Physical context selector remains required.
- Project phase changes from **Phase 0 — Foundation** to **Phase 1 — Research**.

**Conclusion:**  
The project now has a sufficiently stable source of truth to begin structured technical research.

**Next step:**  
Begin Phase 1 with keyboard geometry and ergonomics. In parallel, quantify Context Display requirements before MCU and PCB decisions.

**References / files:**  
- `README.md`
- `assets/images/dvn-65-banner.png`
- `docs/02_PRODUCT_SPEC.md`
- `docs/04_ROADMAP.md`
- `docs/05_DESIGN_DECISIONS.md`
- `docs/07_RESEARCH_BACKLOG.md`

---

## 2026-09-23 — Context selector consolidated into push rotary encoder

**Area:** Product interaction / architecture / ergonomics

**Objective:**  
Simplify the DVN-65 control area and recover top-surface space for a larger Context Display while preserving direct on-device context selection.

**Result:**  
The previous requirement for a separate physical context selector is superseded. Rev 1 will use the **Context Display + push rotary encoder** as the primary local control interface.

Interaction direction:
- encoder rotation navigates menus or adjusts the selected value
- encoder press selects/confirms or enters the on-device interface
- WRITE / CODE / DEV / GAME / CUSTOM can be selected through this interface
- volume, functional-lighting intensity, profiles and future controls may share the same interface
- exact short-press / long-press behavior remains to be prototyped

Mechanical direction:
- Context Display above
- push rotary encoder below
- no dedicated mode-selector mechanism
- recovered upper control-area space should be used to increase useful display area where practical

**Decision impact:**  
- The physical context-selector requirement recorded in the Phase 0 baseline is **SUPERSEDED** by this entry.
- Remove dedicated selector hardware, I/O and mechanical integration from Rev 1 requirements.
- Context Display becomes the primary visual indicator of active context.
- Push rotary encoder becomes the primary local input for context selection and display navigation.

**Next step:**  
Refine the G1R+ control island with the display at the upper edge and the push rotary encoder below, then prototype the interaction flow.


---

## 2026-09-23 — G1R+ v5 geometry candidate

**Area:** Ergonomics / mechanical / product interaction

**Objective:**  
Refine the Phase 1 keyboard geometry into a single printable candidate that preserves ISO-ES familiarity while testing a moderate ergonomic opening and integrating the Context Display + push rotary encoder control area.

**Result:**  
The **G1R+ v5** geometry was selected as the current working candidate for physical validation.

Geometry direction:
- approximately 65%
- ISO-ES familiar letter positions and ISO Enter
- unibody semi-split
- 6° rotation per half / 12° total opening
- conventional row stagger
- split Space for geometry purposes, with both halves acting as Space
- physical arrow cluster retained
- dedicated Del / PgUp / PgDn / Home / End removed and moved to Fn-layer access

Control-area direction:
- Context Display at the upper edge of the right control area
- enlarged display reservation compared with earlier iterations
- push rotary encoder below the display
- no dedicated context-selector hardware

Printable 1:1 A3 and tiled A4 templates were generated for physical posture and reach testing.

**Conclusion:**  
G1R+ v5 is the strongest current Phase 1 candidate, but remains experimental until validated physically. The geometry must not yet be treated as a final PCB or case commitment.

**Decision impact:**  
- G1R+ v5 becomes the baseline for the next geometry/mechanical refinement iteration.
- Final geometry remains **TBD — Research Required**.

**Next step:**  
Validate the 1:1 template physically, then refine the outer case contour, display integration, encoder placement and overall dimensions.

**References / files:**  
- `assets/geometry/phase1/DVN65_G1Rplus_v5_A3_1to1.pdf`
- `assets/geometry/phase1/DVN65_G1Rplus_v5_A4_Tiled_1to1.pdf`

