![Pulsephonelogo](assets/pulsephone.png)

# PulsePhone — Pulse Modular Phone (MCM-iMX93 SoM)

> A modular, open-source smartphone built for repairability, upgradability, and hardware freedom.

Built around the **MCM-iMX93 System-on-Module**, PulsePhone uses **Hirose DF40** board-to-board connectors across all subsystems — keeping modules isolated, swappable, and independently developable.

---

## System Architecture

The **Main Board** is the hub of the system, hosting the MCM-iMX93 SoM, power management, WiFi/BT, onboard DAC, and all signal routing. Every peripheral connects via DF40 connectors following the MBI-Lite standard.

| Module         | Interface          | Role                                               |
|----------------|--------------------|----------------------------------------------------|
| Main Board     | DF40 (host)        | MCM-iMX93 SoM, WiFi/BT, DAC, power management     |
| Display Module | MIPI-DSI + Touch   | Adapter for wide MIPI-DSI display compatibility    |
| Camera Module  | MIPI CSI-2         | Adapter for wide MIPI-CSI camera compatibility     |
| Audio Module   | Analog             | Amp, speaker, headphone, mic                       |

Full connector pinout in [MBI-Lite Specification](MBI-LITE.md).

---

## Project Goals

- One connector standard (DF40) across every module
- Yocto Linux (meta-imx BSP) as primary OS target
- Kit-oriented design — bring your own display and case
- Fully open: KiCad source + mechanical files under GNU GPL-V3.0

---

## Hardware Status

### Main Board — Rev 2
- MCM-iMX93 LGA-140 SoM (NXP iMX93, dual A55 + M33)
- LBEE5KL1YN-814 WiFi/BT module with U.FL antenna connector
- PCM5102A audio DAC routed to SAI port
- TPS63020 buck-boost regulator, AP2112K-3.3 LDO
- TP4056 battery charger, MIC2877 5V boost
- Schematic complete, PCB routed, pre-order review in progress

### Rev 1 — Lessons Learned
- XL1509 EN pin active-low behavior caused 3.3V rail failure (fixed in Rev 2 by switching to AP2112K LDO)
- Test pad size too small for reliable probing (all pads 2mm minimum in Rev 2)
- SoM partial boot activity observed but UART output not confirmed **More on this below*

### Display Module
PCB design complete. Functions as a passive MIPI-DSI adapter for broad display compatibility.

### Camera Module
Design TBD.

### Audio Module
Design in progress.

### Wifi/BT (Prior Module)
Deffered to an embedded system within the main board. (LBEE5KL1YN-814 WiFi/BT)

### Mod Port (NEW DF40 MODULE!)
New connector that allows tinkerers to make their own custom pulsephone modules (ex. custom rfid modules, ir remote module, etc...)! Connector's pinout is stocked with loads of GPIO, UART, and I2C.

---

## Software Target

- **OS:** Yocto Linux with NXP `meta-imx` BSP layer
- **Target:** First Linux boot on A55 cores via SD card
- **Planned:** Custom Yocto distro layer for UI and system configuration

---

## First Bringup Summary (Rev 1) *Failed :(*

- First bringup was not a success as boot only got upto flashing light on the SoM.
- Soldering is to be improved upon with planned access to a Uni FabLab.
- I presume the main cause for failure of Rev 1 was poor soldering quality and electrical faults that were not caught before ordering boards.

---

## Current Status

Rev 2 schematic and PCB complete. Pre-order review week in progress before board order. Targeting first Linux boot on Rev 2 hardware.

---

## Documentation

- [MBI-Lite Module Connector Specification](MBI-LITE.md)
- [Contributing](CONTRIBUTING.md)
- [License](LICENSE)

---

## License

Hardware released under **GNU GPL-V3.0**.
