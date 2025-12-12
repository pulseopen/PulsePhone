![Pulsephonelogo](assets/pulsephone.png)

# PulsePhone — Pulse Modular Phone (MCM-iMX93 SoM)

An experimental modular smartphone platform built around the **MCM-iMX93 System-on-Module (SoM)**.  
Designed for *repairability, upgradability, and hardware freedom*. All external subsystems connect through **Hirose DF12 board-to-board connectors**, allowing isolated module development and easy swapping.

---

## 🧠 System Architecture

| Component | Module Type | Connector | Function |
|-----------|-------------|-----------|----------|
| **Main Board** | Core System | DF12 | Hosts MCM-iMX93 SoM, onboard DAC, and routes all signals |
| **Display Module** | Peripheral | DF12 | MIPI/LVDS (TBD) + Touch Interface |
| **Power + USB Module** | Peripheral | DF12 | Battery input, charging, voltage rails, USB-C (OTG/Data) |
| **Wi-Fi / Bluetooth Module** | Wireless | DF12 | SDIO/UART-based wireless radio |
| **Audio Module** | Peripheral | DF12 | Analog-only amplifier + speaker/headphone/mic interface |

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
> Second prototype! Working on revamping connector standard pinouts and adding i2c!

### Power + USB Module
> First prototype! Working on modifying to fit new standard!

### Wi-Fi / Bluetooth Module
> Not here yet.

### Display Module
> Very early stages of work.

### Audio Module
> Not here yet

---

## 🧩 Project Goals

- **One standardized module connector (DF12) across all subsystems**
- **Analog audio to simplify signal integrity & layout**
- **Linux / Android / Ubuntu Touch compatibility**
- **Full KiCad + mechanical release under open license**

---
## License

- **GNU GPL-V3.0** for hardware
