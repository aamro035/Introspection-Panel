# Introspection-Panel
A space to collaborate on the introspection panel code.
# Introspection Panel – ESP32 Control & LED System

https://github.com/aamro035/Introspection-Panel](https://github.com/aamro035/Introspection-Panel)

This repository contains Version 1 (V1) firmware for the Introspection Panel implemented using a dual-ESP32 architecture. Version control is established using GitHub, with all development tracked from initial commits following defined coding standards.

---

🧠 System Architecture

The system is split into two primary firmware components:

 1️⃣ Input Controller (ESP32 / Arduino-style)

Handles user input and transmits control data via serial.

**Inputs**

* 3 Potentiometers

  * `sun` → Global brightness
  * `mood` → Color mood (blue → orange → red)
  * `water` → Cascading LED activation level
  *  2 Buttons

  * Right & Left toggle buttons (latched state)

**Responsibilities**

* Reads analog and digital inputs
* Applies debouncing and toggle logic
* Sends formatted serial data:

  ```
  sun,mood,water,rightToggle,leftToggle
  ```

---

### 2️⃣ LED Controller (ESP32)

Receives serial data and drives LEDs accordingly.

**Outputs**

* Discrete LEDs (PWM-controlled groups)
* WS2812 addressable LED strips (flower petals)

**Behavior**

* `sun` controls overall brightness
* `mood` controls LED color mapping
* `water` controls cascading activation levels
* Button toggles enable/disable left/right LED groups

---

## 📦 Libraries & Dependencies

All libraries and dependencies are explicitly identified, versioned, and sourced within the code to ensure reproducibility.

### Required Libraries

* **Adafruit NeoPixel**

  * Purpose: WS2812 LED strip control
  * Source: [https://github.com/adafruit/Adafruit_NeoPixel](https://github.com/adafruit/Adafruit_NeoPixel)
  * Installed via Arduino Library Manager

### Built-in Frameworks

* Arduino Core for ESP32
* HardwareSerial (`Serial`, `Serial2`)
* PWM / GPIO APIs

---

## 📐 Coding Standards

The repository follows documented coding standards, applied consistently across all files:

* Descriptive variable and constant naming
* Logical file and responsibility separation
* In-line comments for functional clarity
* Structured setup / loop organization
* Clear state management for inputs and outputs

---

## 🧪 Versioning

* **V1 Firmware** finalized for each prototype
* Stable baseline for further iterations and feature expansion
* All changes tracked via GitHub version control

---

## 🚀 Status

✅ Repository established
✅ Version control active
✅ Libraries documented
✅ V1 prototype firmware complete

---

*This project serves as a reproducible, modular foundation for interactive light-based installations using ESP32 microcontrollers.*
