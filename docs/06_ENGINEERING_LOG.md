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
