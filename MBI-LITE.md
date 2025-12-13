# MBI-Lite Pinout Specification ( Modular Board Interconnect )

*A compact block-based pinout description for PulsePhone DF-12 modules*

---

## 1. Overview

MBI-Lite is the simplified connector standard for PulsePhone modules that **do not require high-speed signals**. It divides the DF-12 pins into consistent functional blocks while keeping flexibility for future expansion.

This standard applies to **general-purpose modules only**. Display and Camera modules have their own dedicated pinouts.

**Dev Note**: DF-12 Connectors being 60pin and not 30pin, is because 60pin provides a more mechanically stable connector which is less likely to disconnect!

---

## 2. Block Structure

MBI-Lite defines four primary pin groups:

---

## A. Power Block (Pins 1–4)

Handles all system power rails.

| Pin | Name | Description                       |
| --- | ---- | --------------------------------- |
| 1   | 3V3  | Regulated 3.3V rail               |
| 2   | 5V   | Boosted 5V rail                   |
| 3   | BAT  | Direct battery voltage (3.7–4.2V) |
| 4   | GND  | Ground reference                  |

**Rules:**

* Modules must **never** feed power back into any rail.
* BAT is raw battery voltage and must be treated with care.

---

## B. Control Block (Pins 5–7)

Used for module configuration and detection.

| Pin | Name   | Description                                |
| --- | ------ | ------------------------------------------ |
| 5   | SDA    | I²C data                                   |
| 6   | SCL    | I²C clock                                  |
| 7   | DETECT | Module pulls low (10kΩ) to signal presence |

**Rules:**

* I²C is reserved for metadata, control, and low-bandwidth activity.
* All modules must expose DETECT.

---

## C. Data Block (Pins 8–9)

General-purpose communication lines.

| Pin | Name  | Description                       |
| --- | ----- | --------------------------------- |
| 8   | DATA1 | Configurable: UART/SPI/1-Wire/etc |
| 9   | DATA2 | Configurable: UART/SPI/etc        |

Possible uses:

* UART TX/RX
* SPI MOSI/MISO
* GPIO
* PWM
* Software-protocol signaling

---

## D. Custom Block (Pins 10+)

Extra pins for module-specific features. These pins allow more advanced modules without forcing global changes.

Below is the **recommended standard mapping** for consistency. Modules may implement only what they need.

---

## 3. Custom Block Pin Recommendations (Pins 10–25)

| Pin | Name      | Purpose                              |
| --- | --------- | ------------------------------------ |
| 10  | UART_TX   | Optional 3.3V UART transmit          |
| 11  | UART_RX   | Optional 3.3V UART receive           |
| 12  | SPI_MOSI  | SPI master-out/slave-in              |
| 13  | SPI_MISO  | SPI master-in/slave-out              |
| 14  | SPI_SCK   | SPI clock                            |
| 15  | SPI_CS0   | SPI chip-select 0                    |
| 16  | USB_DP    | USB D+ (device mode)                 |
| 17  | USB_DN    | USB D− (device mode)                 |
| 18  | I2S_WS    | I²S word-select / LRCK               |
| 19  | I2S_BCLK  | I²S bit clock                        |
| 20  | I2S_SDOUT | I²S serial data (module → mainboard) |
| 21  | I2S_SDIN  | I²S serial data (mainboard → module) |
| 22  | ADC0      | Analog input 0 (0–3.3V)              |
| 23  | ADC1      | Analog input 1 (0–3.3V)              |
| 24  | PWM0      | PWM output 0                         |
| 25  | PWM1      | PWM output 1                         |

---

## 4. Reserved / Future Pins (26–31)

Pins 26–31 are reserved for:

* Future system-level features
* Additional GPIOs
* Optional high-speed lanes (if needed later)

These should remain unassigned unless stated in a future revision.

---

## 5. Electrical & Integration Rules

* **Voltage:** All digital pins operate at **3.3V logic**.
* **Default state:** All pins 10+ default to **high-impedance** until claimed via I²C module profile.
* **USB D+/D−:** Must be routed as a differential pair with impedance control.
* **UART:** Add small series resistors (22–100Ω recommended).
* **SPI:** Document clock polarity/phase.
* **I²S:** Modules must specify clock master/slave role.
* **ADC:** Specify input impedance and protection.
* **PWM:** Logic-level only, requires external drivers for loads.
* **ESD:** All externally accessible signals must have ESD protection compatible with handheld devices.

---

## 6. Backwards Compatibility

MBI-Lite is designed so that:

* Modules using pins 10+ still work on boards that only support pins 1–9.
* Modules must provide an I²C descriptor listing which optional pins they use.
* DATA1/DATA2 should be used as fallback communication when advanced pins are unavailable.

---

## 7. Quick Reference

```
[Power]
1 – 3.3V
2 – 5V
3 – BAT
4 – GND

[Control]
5 – SDA
6 – SCL
7 – Detect

[Data]
8 – Data1
9 – Data2

[Custom]
10–25 Recommended functions
26–31 Reserved
```

---

# End of MBI-Lite Specification
