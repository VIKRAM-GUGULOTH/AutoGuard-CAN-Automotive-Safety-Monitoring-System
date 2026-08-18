# 🏎️ AutoGuard CAN: Intelligent Automotive Safety and Monitoring System

An intelligent CAN-based automotive safety and monitoring system developed using LPC2129 that enables real-time vehicle monitoring, distributed embedded control, accident detection, and dashboard visualization.

## 📌 Overview

AutoGuard CAN is a real-time embedded automotive monitoring system built using the Controller Area Network (CAN) protocol.

The system is designed to continuously monitor important vehicle parameters and provide real-time information through an LCD dashboard.

The system monitors:

- ⛽ Fuel Level
- 🔁 Vehicle Indicator Status
- 💥 Accident Conditions
- 🛡️ Airbag Deployment Status

Multiple embedded nodes communicate through the CAN bus, enabling reliable data exchange between different vehicle subsystems.

## 🎯 Aim

To develop an intelligent automotive safety and monitoring system using Controller Area Network (CAN) communication to enhance:

- Vehicle safety
- Real-time monitoring
- Distributed embedded control
- Accident detection
- Fuel percentage monitoring
- Indicator control

## ⚙️ System Architecture

The system consists of three CAN-enabled embedded nodes connected through a common CAN bus.
<img width="990" height="740" alt="image" src="https://github.com/user-attachments/assets/5be9b48a-85cf-4990-bf05-fe1f58340eae" />

                                      **Figure 1. AutoGuard CAN System Architecture**

The system consists of three CAN-enabled embedded nodes connected through a common CAN bus.

### Project Nodes

- **Main Node** – Central dashboard and monitoring node
- **Indicator Node** – Controls vehicle indicator signals
- **Fuel Node** – Monitors fuel level and sends fuel information

## 🧠 Project Nodes

### 1️⃣ Main Node

The Main Node is the central node responsible for monitoring and displaying vehicle information.

### Functions

- Displays fuel percentage on LCD
- Displays airbag status
- Sends indicator signals to the Indicator Node
- Receives fuel information from the Fuel Node
- Reads accelerometer data
- Detects possible accident conditions
- Determines airbag deployment status

### 2️⃣ Fuel Node

The Fuel Node is responsible for fuel monitoring.

- Reads fuel gauge sensor information using ADC
- Processes the fuel sensor value
- Determines fuel percentage
- Sends fuel information to the Main Node through CAN

### 3️⃣ Indicator Node

The Indicator Node is responsible for controlling vehicle indicator signals.

- Receives CAN messages from the Main Node
- Processes indicator control commands
- Controls the indicator LEDs
- Provides left and right indicator functionality

## 🧰 Hardware Requirements

| Component | Purpose |
|---|---|
| LPC2129 | Embedded Controller |
| MCP2551 | CAN Transceiver |
| LCD (20×4) | Dashboard Display |
| MMA7660 | Accelerometer Sensor |
| LEDs | Indicator Simulation |
| Fuel Gauge | Fuel Level Input |
| Switches | Indicator Input |
| USB-UART Converter | Programming Interface |

## 💻 Software Requirements

- **Embedded C**
- **Keil µVision / Keil-C Compiler**
- **Flash Magic**

## 🛠️ Project Modules

### 📺 LCD Module

The LCD is used as the vehicle dashboard to display:

- Fuel percentage
- Indicator status
- Airbag status
- Safe condition
- Dashboard information

### 📈 ADC Module

The ADC module is used by the Fuel Node to read the fuel gauge sensor information. The obtained fuel information is processed and transmitted to the Main Node through CAN.

### 🚖 CAN Module

The CAN module handles communication between the different vehicle nodes.

- CAN transmission
- CAN reception
- Data exchange between nodes
- CAN frame communication

### 🚨 Interrupt Module

External interrupts are used for the indicator switches:

- **SW1** – Indicator input
- **SW2** – Indicator input

When an interrupt occurs, the Main Node sends the appropriate indicator control signal to the Indicator Node through CAN.

### 📄 I2C Module

The I2C interface is used for communication with the MMA7660 accelerometer sensor.

### 📐 Accelerometer Module

The accelerometer module reads acceleration information and is used for accident detection.

The measured acceleration is analysed against predefined safety threshold limits. If the acceleration exceeds the configured safety threshold, the system identifies an accident condition and displays the corresponding airbag deployment status on the LCD.

## 📡 CAN Communication

The CAN bus provides communication between the Main Node, Indicator Node, and Fuel Node.

| CAN ID | Data | Description |
|---|---|---|
| 1 | Fuel Percentage | Fuel Node → Main Node |
| 2 | `0x01` | Left Indicator |
| 2 | `0x02` | Right Indicator |

## 🔄 Project Workflow

1. ⛽ Fuel Node reads the fuel gauge using ADC.
2. Fuel percentage is calculated.
3. Fuel information is transmitted to the Main Node through CAN.
4. Main Node receives the fuel information.
5. Fuel percentage is displayed on the LCD.
6. SW1/SW2 generate external interrupts.
7. Main Node sends the appropriate indicator command through CAN.
8. Indicator Node receives the command.
9. Indicator LEDs are activated accordingly.
10. MMA7660 provides accelerometer information.
11. Main Node analyses the acceleration data.
12. If an accident condition is detected, the airbag status is displayed on the LCD.

## 📸 Hardware Implementation

### 🔧 Complete Hardware Setup
<img width="4080" height="3060" alt="project1 jpg" src="https://github.com/user-attachments/assets/2081fcba-89af-4a71-92b6-f7d6cfd6ac92" />


                                     **Figure 2. Actual Complete Hardware Setup**

*Actual hardware implementation of the AutoGuard CAN system.*

## 🖥️ Dashboard Output
### ✅ Safe Condition
<img width="863" height="426" alt="image" src="https://github.com/user-attachments/assets/41a20ac9-1e8d-4aa7-a74c-157a55e183d6" />


                                     **Figure 3. LCD Dashboard – Safe Condition**

The LCD dashboard displays the indicator status, fuel percentage, and SAFE CONDITION during normal operation.

### 🚨 Accident / Airbag Status
<img width="849" height="429" alt="image" src="https://github.com/user-attachments/assets/676c465d-c6cc-42ce-8cc7-9904cbf92dbd" />


                                     **Figure 4. LCD Dashboard – Airbag Opened**

When an accident condition is detected, the LCD dashboard displays the corresponding AIRBAG: OPENED status.

## 🚀 Features

- ✔ Real-time vehicle monitoring
- ✔ CAN-based distributed architecture
- ✔ Fuel level monitoring
- ✔ Indicator control system
- ✔ Accelerometer-based accident detection
- ✔ Airbag deployment status indication
- ✔ LCD dashboard display
- ✔ External interrupt-based indicator control
- ✔ Reliable inter-node CAN communication

## ✨ Applications

- 🚗 Automotive dashboard systems
- 🛡️ Vehicle safety systems
- 🔌 CAN-based embedded systems
- 🚨 Accident detection systems
- ⚙️ Distributed automotive control systems
- 🎓 Automotive embedded-system learning and research

## 💡 Future Enhancements

- GPS-based real-time vehicle tracking
- GSM-based accident alerts
- Temperature monitoring
- Tire pressure monitoring
- Battery monitoring
- Mobile/web dashboard
- Cloud-based data logging
- SD card data logging

## 🏁 Conclusion

AutoGuard CAN: Intelligent Automotive Safety and Monitoring System demonstrates how the Controller Area Network (CAN) protocol enables reliable communication between multiple vehicle subsystems.

The system integrates:

- Fuel monitoring
- Indicator control
- Accelerometer-based accident detection
- Airbag status indication
- LCD dashboard visualization

The project provides practical experience with Embedded C, LPC2129 architecture, ADC, interrupts, I2C, accelerometer interfacing, and CAN communication.

## 👨‍💻 Author

GUGULOTH VIKRAM

Electronics and Communication Engineering

National Institute of Technology Arunachal Pradesh

## 📜 License

This project is developed for academic and learning purposes.

You are free to modify and enhance the project with proper credit.

⭐ If you find this project useful, consider giving it a star on GitHub!
