# DVN High-Level Architecture

**Status:** Conceptual / evolving

## System overview

```text
┌──────────────────────────────┐
│          DVN Studio          │
│      C# / .NET / Avalonia    │
└──────────────┬──────────────┘
               │
        USB configuration
        protocol / HID
               │
┌──────────────▼───────────────┐
│        DVN Firmware          │
│         QMK + DVN            │
│                              │
│ modes                        │
│ keymap                       │
│ module manager               │
│ optical state                │
│ persistent configuration     │
└───────┬─────────────┬────────┘
        │             │
        │             │
┌───────▼──────┐  ┌───▼────────────────┐
│ Core PCB     │  │ DVN Module Interface│
│              │  │                     │
│ matrix       │  │ discovery           │
│ MCU          │  │ communication       │
│ USB-C        │  │ power               │
│ RGB          │  │ hot attachment TBD  │
│ encoder      │  └───────┬─────────────┘
└───────┬──────┘          │
        │                 ▼
        │            External modules
        │
        ▼
DVN Adaptive Legends
```

## 1. Core hardware
The main keyboard PCB is responsible for:
- key matrix scanning
- MCU
- USB-C connection
- hot-swap MX switches
- RGB/optical illumination
- physical mode selector
- encoder
- module interface
- reset/boot/debug access
- persistent configuration support

MCU is not yet selected.

## 2. Firmware layer
Base: QMK unless later research justifies a change.

QMK should provide commodity keyboard functionality such as:
- USB HID
- matrix scanning
- debouncing
- layers
- keycodes
- NKRO
- bootloader support where applicable

DVN-specific firmware should provide:
- Context System
- module discovery/configuration
- Adaptive Legends control
- DVN configuration protocol
- profile persistence
- Action Key behavior

## 3. DVN Studio
Desktop configuration application.

Responsibilities:
- discover DVN devices
- read device capabilities
- edit keymaps
- configure modes
- edit CUSTOM mode
- create macros
- configure modules
- configure encoder
- configure Action Key
- control functional lighting
- import/export profiles
- diagnostics
- firmware/device information

The application should not be required after configuration is written to the keyboard.

## 4. DVN Protocol
Communication layer between DVN Studio and firmware.

Potential transport:
- USB HID / Raw HID

Not yet confirmed.

Conceptual commands:
- GET_DEVICE_INFO
- GET_KEYMAP
- SET_KEY
- SET_LAYER
- SET_MODE
- SET_RGB
- SET_ENCODER
- GET_MODULES
- SET_MODULE_CONFIG
- SAVE_PROFILE
- GET_DIAGNOSTICS

Protocol should eventually be versioned.

## 5. DVN Context System
Physical operating states:
- WRITE
- CODE
- DEV
- GAME
- CUSTOM

Changing context may modify:
- key actions
- optical legends
- functional lighting
- encoder behavior
- module behavior
- Action Key behavior

The core alphabetic layout should remain familiar.

## 6. DVN Adaptive Legends
Optical subsystem that makes alternate legends appear or become dominant depending on context.

Initial research direction:
- RGB or selected-wavelength LEDs
- optical filters
- printed films/PET
- masks
- diffusion
- relegendable keycaps for early prototypes

Must be validated experimentally before full keyboard integration.

## 7. DVN Module Interface
Conceptual side-module architecture.

Mechanical direction:
- alignment guides
- magnets
- pogo pins

Electrical/protocol decisions are TBD.

The interface should eventually support:
- module identification
- module type
- capabilities
- firmware/protocol version
- configuration

## 8. Data persistence
Required behavior:
1. Configure device in DVN Studio.
2. Save configuration to keyboard.
3. Disconnect from PC.
4. Connect to another machine.
5. Keyboard retains its behavior.

Exact storage mechanism depends on MCU/platform selection.

## 9. Architecture principles
- clear boundaries between hardware, firmware and software
- version interfaces rather than tightly coupling components
- prototype risky subsystems independently
- use existing reliable foundations where appropriate
- avoid unnecessary complexity
- preserve future extensibility without overengineering Rev 1
