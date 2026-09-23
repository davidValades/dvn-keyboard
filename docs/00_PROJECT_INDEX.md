# DVN Project Index

## Project
**DVN — Dynamic Visual Nexus**

First product: **DVN-65**

Repository: `davidValades/dvn-keyboard`

## Purpose
This file is the navigation map for the DVN project knowledge base. Use it to identify the authoritative source for each type of information.

## Core documents

### `01_PRODUCT_VISION.md`
Stable product vision:
- mission
- target user
- product philosophy
- differentiators
- long-term direction
- definition of success

### `02_PRODUCT_SPEC.md`
Current product requirements. This is the main source of truth for **what DVN must do**.

### `03_ARCHITECTURE.md`
High-level system architecture: hardware, firmware, DVN Studio, Context Display, modules, protocol and optical system.

### `04_ROADMAP.md`
Current phase, milestones, dependencies and next steps.

### `05_DESIGN_DECISIONS.md`
Confirmed, pending, experimental, rejected and future decisions.

### `06_ENGINEERING_LOG.md`
Chronological engineering journal for experiments, prototypes, measurements, failures and discoveries.

### `07_RESEARCH_BACKLOG.md`
Questions and topics still requiring investigation.

## Future specialized documents
Create only when enough information exists:
- `DEVELOPER_LAYOUT.md`
- `OPTICAL_SYSTEM.md`
- `MODULE_STANDARD.md`
- `ELECTRONICS.md`
- `DVN_PROTOCOL.md`
- `DVN_STUDIO.md`
- `CONTEXT_DISPLAY.md`
- `MANUFACTURING.md`
- `BOM.md`
- `adr/`

## Source-of-truth rules
If information conflicts, prefer:
1. Latest approved ADR
2. `02_PRODUCT_SPEC.md`
3. `03_ARCHITECTURE.md`
4. `05_DESIGN_DECISIONS.md`
5. `06_ENGINEERING_LOG.md`
6. Conversation context

A conversation does not silently override documented decisions. Important changes should be reflected in the relevant project source.
