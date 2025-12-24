![Pulsephonelogo](assets/pulsephone.png)

# PulsePhone — Pulse Modular Phone (MCM-iMX93 SoM)

An experimental modular smartphone platform built around the **MCM-iMX93 System-on-Module (SoM)**.  
Designed for *repairability, upgradability, and hardware freedom*. All external subsystems connect through **Hirose DF40 board-to-board connectors**, allowing isolated module development and easy swapping.

---

## 🧠 System Architecture

| Component | Module Type | Connector | Function |
|-----------|-------------|-----------|----------|
| **Main Board** | Core System | DF40 | Hosts MCM-iMX93 SoM, onboard DAC, and routes all signals |
| **Display Module** | Peripheral | DF40 | MIPI/LVDS (TBD) + Touch Interface |
| **Wi-Fi / Bluetooth Module** | Wireless | DF40 | SDIO/UART-based wireless radio |
| **Audio Module** | Peripheral | DF40 | Analog-only amplifier + speaker/headphone/mic interface |

---

## 🔌 DF40 Connector Interface (Signal Groups)

>[Moved to MBI-Lite Specification](MBI-LITE.md)

---

## 🛠 Development Notes 

### Main Board
> Second Revision!
> Revamping design.

### Wi-Fi / Bluetooth Module
> Not here yet.

### Display Module
> Very VERY early stages of work.

### Audio Module
> Not here yet

---

## 🧩 Project Goals

- **One standardized module connector (DF40) across all subsystems**
- **Analog audio to simplify signal integrity & layout**
- **Linux (Debian + Phosh) / Android / Ubuntu Touch compatibility**
- **Full KiCad + mechanical release under open license**

---
## License

- **GNU GPL-V3.0** for hardware

---
## Documentation

- [MBI-Lite Module Connector Specification](MBI-LITE.md)
- [Contributing](CONTRIBUTING.md)
- [License](LICENSE)

---
## Current Project Status

- Slow pace since school is a **priorty**!
- Not ready to boot anything
- Working on power distribution solutions
