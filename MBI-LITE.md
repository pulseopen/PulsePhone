# MBI-Lite Specification — Modular Board Interconnect

MBI-Lite is the connector standard for PulsePhone's general-purpose DF-40 modules. Two blocks: Power and a flexible Custom block. Display and Camera have their own dedicated pinouts.

> **Dev Note:** DF-40 connectors are 34-pin instead of 30-pin — better mechanical stability, and honestly, 30-pin options were just hard to find.

---

## Pin Map

### Power (Pins 1–4)

| Pin | Name | Description                    |
|-----|------|--------------------------------|
| 1   | 3V3  | Regulated 3.3V rail            |
| 2   | 5V   | Boosted 5V rail                |
| 3   | BAT  | Raw battery voltage (3.7–4.2V) |
| 4   | GND  | Ground reference               |

Don't back-feed any rail. BAT is raw battery voltage — treat it accordingly.

---

### Custom Block (Pins 5–22)

18 pins, fully open. Assign them however your module needs — GPIO, UART, SPI, I²S, USB, ADC, PWM, whatever fits. No mandated mapping.

Constraints:
- All pins operate at **3.3V logic**
- All pins default to **high-impedance** until configured
- Any differential pair must be routed with impedance control, Include GND pins between EVERY differential pair.
- Anything externally accessible needs handheld-grade ESD protection

**Documentation is required.** For every pin you use, you must provide a clear description of its assignment, the reasoning behind it, any relevant electrical characteristics (pull-ups, drive strength, impedance, etc.), and how it interacts with the rest of the module. Undocumented pin usage is not acceptable.

---

### Reserved (Pins 23–34)

Reserved for future GPIOs, system features, or optional high-speed lanes. Leave unassigned unless stated in a future revision.

---

## Electrical Rules

A few interface-specific things to keep in mind:

- **UART** — 22–100Ω series resistors recommended
- **SPI** — document clock polarity/phase in your module's profile
- **I²S** — declare whether your module is clock master or slave
- **ADC** — specify input impedance; add overvoltage protection
- **PWM** — logic-level only, add an external driver for any real load

---

## Backwards Compatibility

Modules that use pins beyond the basics will still work on boards that only implement a subset — they just won't use those features. Each module should document which pins it uses.
