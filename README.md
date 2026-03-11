![Pulsephonelogo](assets/pulsephone.png)

# PulsePhone — Pulse Modular Phone (MCM-iMX93 SoM)

> A modular, open-source smartphone built for repairability, upgradability, and hardware freedom.

Built around the **MCM-iMX93 System-on-Module**, PulsePhone uses **Hirose DF40** board-to-board connectors across all subsystems — keeping modules isolated, swappable, and independently developable.

---

## System Architecture

The **Main Board** is the hub of the system, hosting the MCM-iMX93 SoM, an onboard DAC, and all signal routing. Every peripheral connects to it via DF40 connectors.

| Module          | Interface         | Role                                        |
|-----------------|-------------------|---------------------------------------------|
| Main Board      | DF40 (host)       | MCM-iMX93 SoM, DAC, signal routing          |
| Display Module  | MIPI/LVDS + Touch | Adapter for wide MIPI-DSI display compatability.   |
| Camera Module  | MIPI CSI-2 | Adapter for wide MIPI-CSI camera compatability.   |
| Audio Module    | Analog            | Amp, speaker, headphone, mic      |

Full connector pinout in [MBI-Lite Specification](MBI-LITE.md).

---

## Project Goals

- One connector standard (DF40) across every module
- Linux (Debian + Phosh), Android, and Ubuntu Touch compatible
- Fully open: KiCad source + mechanical files under GNU GPL-V3.0

---

## Development Notes

### Main Board
> First prototype!
> Revamping design.
> PCB Design in final polishing and bug fix stages!

### Wi-Fi / Bluetooth Module
> Not here yet.

### Display Module
> PCB Design DONE!
> This module acts like an adapter, so PulsePhone can have a wide range of MIPI-DSI displays to be compatible with.

### Camera Module
> Design TBD

### Audio Module
> Design Started

### Radio Module
> **NOT** included in first prototype due to radio ciruitry complexity slowing down progress of getting to a first boot.

---

## Current Project Status

- Almost ready to boot something.
- Working on wrapping up design for main board.

---

## Documentation

- Check out the [Wiki](https://github.com/pulseopen/PulsePhone/wiki)
- [MBI-Lite Module Connector Specification](MBI-LITE.md)
- [Contributing](CONTRIBUTING.md)
- [License](LICENSE)

---

## License

Hardware released under **GNU GPL-V3.0**.
