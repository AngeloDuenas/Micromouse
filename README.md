# 🐭 Micromouse Robot PCB (Altium Designer)

![Status](https://img.shields.io/badge/status-completed-brightgreen)
![PCB](https://img.shields.io/badge/PCB-2--Layer-blue)
![MCU](https://img.shields.io/badge/MCU-STM32F411RE-orange)
![Tool](https://img.shields.io/badge/Designed%20With-Altium%20Designer-red)

A custom-designed **Micromouse robot PCB** created in **Altium Designer**, integrating sensing, motor control, and power regulation into a compact 2-layer board.

---

## 📌 Overview

This project focuses on the **hardware design** of a Micromouse robot, including:

- Infrared wall detection system  
- Dual motor driver with encoder interface  
- IMU sensor integration  
- Power regulation (3.3V & 6V rails)  
- Custom 2-layer PCB layout  

---

## 🧠 System Block Diagram

```
                +----------------------+
                |   STM32F411RE MCU   |
                +----------+----------+
                           |
        +------------------+------------------+
        |                  |                  |
        v                  v                  v

+---------------+   +---------------+   +------------------+
|   IR Sensors  |   |      IMU      |   |  Motor Driver    |
|               |   | LSM6DSRTR     |   |   DRV8833        |
+-------+-------+   +-------+-------+   +--------+---------+
        |                   |                    |
        |                   |                    v
        |                   |            +------------------+
        |                   |            |  DC Motors (x2)  |
        |                   |            |  + Encoders      |
        |                   |            +------------------+
        |
        v
+------------------+
| Wall Detection   |
+------------------+

        Power System
+-------------------------------------------+
| Battery → 6V Reg → Motor Driver           |
|         → 3.3V Reg → MCU + Sensors        |
+-------------------------------------------+
```

---

## ⚙️ Hardware Architecture

### 🧩 Microcontroller
- STM32F411RE (NUCLEO-64 form factor)
- Interfaces with sensors, motor driver, and encoders

---

### ⚡ Motor Control
- DRV8833 Dual H-Bridge
- Drives two DC motors
- Supports encoder feedback

---

### 👀 Sensor System

#### IR Wall Detection
- 4 × IR Emitters (SFH 4555)
- 4 × Photodiodes (1540051EA3590)
- MOSFET switching (BS170)

#### IMU
- LSM6DSRTR (Accelerometer + Gyroscope)
- I2C interface

---

### 🔋 Power System
- LD1117V33 → 3.3V rail
- L7806CV → 6V rail
- Battery input (JST connector)
- On/off switch

---

## 🧾 Bill of Materials

Main components include:

- STM32 NUCLEO-F411RE  
- DRV8833 Motor Driver  
- LSM6DSRTR IMU  
- IR emitters & photodiodes  
- Pololu gearmotors with encoders  
- Voltage regulators  
- Passive components  

**Estimated Total Cost: ~$113.86**

---

## 🖥️ PCB Design

- 2-layer PCB  
- Compact layout for Micromouse chassis  
- Designed for:
  - Clean routing  
  - Stable power delivery  
  - Minimal noise  

---

## 📂 Repository Structure

```
/hardware
 ├── schematics/
 ├── pcb/
 ├── outputs/
 └── BOM/

README.md
```

---

## 🛠️ Tools Used

- Altium Designer  
- Digikey / Mouser / Pololu (components)  
- PCBWay / JLCPCB (fabrication)  

---

## 📈 Future Improvements

- Integrate MCU directly onto PCB  
- Add battery management system  
- Improve sensor calibration  
- Further reduce PCB size  

---

## 👤 Author

Angelo Duenas  
Micromouse PCB Project – 2026  

---

## 📜 License

MIT License
