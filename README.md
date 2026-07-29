# PWM Signal Generation via Three Analog Techniques

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![OrCAD PSpice](https://img.shields.io/badge/Simulation-OrCAD%20PSpice-orange.svg)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen.svg)

This repository contains the design, **OrCAD PSpice** simulations, and physical breadboard implementations of **Pulse Width Modulation (PWM)** signal generation circuits utilizing three distinct analog methods:
1. **Transistor-based** (BJT Astable Multivibrator)
2. **Op-Amp-based** (LM358 Comparator & Triangle Waveform Generation)
3. **Timer IC-based** (NE555 in Astable Mode with asymmetrical charging paths)

---

## 📌 Project Overview

Pulse Width Modulation (PWM) is an essential technique used across power electronics, motor drivers, audio synthesis, and signal processing. The objective of this project is to explore, compare, and validate analog PWM generation methods by matching theoretical calculations, simulation outputs, and physical oscilloscope measurements.

* **Course:** EEM0306 Electronics Laboratory II
* **Group:** G20
* **Authors:** Kuban Uygar KURT & Jess Edmond RAZAFIMANOVOLILY

---

## ⚡ Implementation Methods & Component List

### 1. Transistor-Based PWM Generator
Generates a square wave via an asymmetric BJT astable multivibrator circuit. Adjusting the RC time constants alters the charge/discharge periods to control the duty cycle.
* **Transistors:** 2x 2N3904
* **Resistors:** 2x $4.7\text{ k}\Omega$, $477\text{ k}\Omega$, $390\text{ k}\Omega$
* **Capacitors:** 2x $10\text{ nF}$

### 2. Op-Amp-Based PWM Generator
Compares a generated triangle wave against a DC reference voltage using an operational amplifier in comparator mode. Adjusting the reference voltage fine-tunes the output duty cycle.
* **Op-Amps:** 3x LM358
* **Resistors:** $4.7\text{ k}\Omega$, 3x $10\text{ k}\Omega$, 2x $1\text{ k}\Omega$, $6.2\text{ k}\Omega$, $2.7\text{ k}\Omega$
* **Potentiometer:** $100\text{ k}\Omega$ (Duty Cycle Control)
* **Capacitors:** 2x $100\text{ nF}$, $10\ \mu\text{F}$, $47\text{ nF}$

### 3. NE555 Timer IC PWM Generator
Operates the 555 IC in astable mode, employing diodes to split the capacitor's charging and discharging pathways to achieve independent duty cycle adjustment.
* **IC:** NE555 Timer
* **Diodes:** 1N4002
* **Resistors:** 2x $10\text{ k}\Omega$, $18\text{ k}\Omega$
* **Capacitors:** $0.1\ \mu\text{F}$, $100\text{ nF}$ ($0.01\ \mu\text{F}$ control)

---

## 🔬 Comparison & Key Observations

| Feature | Transistor (BJT) | Op-Amp (LM358) | IC (NE555) |
| :--- | :--- | :--- | :--- |
| **Complexity** | Low | High | Medium |
| **Duty Cycle Stability** | Low | High | Very High |
| **Ease of Tuning** | Fixed / Hard to tune dynamically | Flexible (via Potentiometer) | Highly Compact & Easy |
| **Best Application** | Basic oscillation needs | High-precision analog control | Industrial standard power/motor control |

---

## 📷 Results & Testing

Both SPICE simulation wave plots and physical oscilloscope captures are documented for each method:
- **Simulations:** Conducted using OrCAD PSpice software to verify duty cycles and transient response.
- **Physical Build:** Breadboard setup tested using a UNI-T Digital Storage Oscilloscope.

---

## 🚀 Future Enhancements

- Integrate microcontrollers (e.g., STM32, Arduino, or ESP32) for digital/software-based PWM generation with variable frequency and high-resolution duty cycle control.
- Add a power MOSFET output stage to drive high-current loads like DC motors or high-power LEDs directly.

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
