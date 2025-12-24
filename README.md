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
| **Wi-Fi / Bluetooth Module** | Wireless | DF12 | SDIO/UART-based wireless radio |
| **Audio Module** | Peripheral | DF40 | Analog-only amplifier + speaker/headphone/mic interface |

---

## 🔌 DF12 Connector Interface (Signal Groups)

| Pin Group | Purpose |
|-----------|---------|
| **Power Distribution** | VSYS (Battery), 5V, 3.3V |
| **USB 2.0 Data** | D+ / D− directly from SoM |
| **Control / GPIO** | Enable, IRQ, I2C (as needed) |
| **Analog Audio (Main ➝ Audio Module)** | L_OUT, R_OUT, AGND — *no I²S routed* |

> Digital audio stays on the **main board only**, with DAC output sent as **analog** to the audio module.

---

## 🛠 Development Notes 

### Main Board
> Second Revision!
> Working on revamping connector standard pinouts and adding i2c.

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
