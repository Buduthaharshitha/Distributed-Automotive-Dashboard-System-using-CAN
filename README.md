Here’s your cleaned README with the **Repository section removed** 👇

---

# 🚗 Distributed Automotive Dashboard using CAN on STM32F429ZIT6

## 📌 Overview

This project implements a **distributed automotive dashboard system** using multiple STM32F429ZIT6 nodes communicating over the Controller Area Network.
It replicates how real vehicle ECUs exchange data and display critical parameters in real time.

---

## 🧠 System Architecture

The system consists of three independent nodes connected via CAN bus:

### 🔹 Node 1 – Vehicle Parameters Unit

* Indicator status
* Vehicle speed
* Temperature

### 🔹 Node 2 – Engine & Time Unit

* Gear position
* Engine RPM (via ADC)
* Real-Time Clock (RTC)

### 🔹 Node 3 – Dashboard Unit

* Receives CAN messages from all nodes
* Applies hardware filtering
* Displays formatted data via UART

---

## 🛠 Hardware Requirements

* 3 × STM32F429ZIT6
* CAN Transceiver (MCP2551 / TJA1050)
* UART Terminal (Tera Term)
* Potentiometer (for RPM input)
* Switches & LEDs
* Temperature Sensor (DHT11)

---

## 🔄 CAN Communication Details

* Mode: Normal Mode
* Identifier: Standard (11-bit)
* Communication: Interrupt-driven
* Filtering: Hardware-based (Mask mode)
* Architecture: Multi-node distributed system

### 📡 CAN Message IDs

| Parameter   | CAN ID |
| ----------- | ------ |
| Indicator   | 0x101  |
| Speed       | 0x201  |
| Temperature | 0x301  |
| Gear        | 0x401  |
| RPM         | 0x501  |
| Time        | 0x601  |

---

## ⚙️ Key Features

* Interrupt-based CAN reception
* Efficient ISR-safe design
* Hardware CAN filtering
* ADC-based RPM measurement
* RTC integration
* UART real-time dashboard display
* Modular and scalable firmware

---

## 🧩 Software Design

* Developed using STM32 HAL drivers (CubeMX)
* CAN RX interrupt callback mechanism
* Flag-based processing in main loop
* Use of `volatile` variables for ISR safety
* Clean and maintainable code structure

---

## 📊 Sample Output

```id="output1"
IND   Speed   Temp   Gear   RPM   Time  
L      45      32     G2     67   12:45:33
```

---

## 🎯 Learning Outcomes

* Understanding CAN bus communication
* Configuring CAN filters (Mask mode)
* Interrupt handling in embedded systems
* Designing distributed ECU architecture
* Real-time embedded system implementation

---

## 🚀 Future Enhancements

* FreeRTOS integration for multitasking
* CAN error handling & diagnostics
* LCD/OLED graphical dashboard
* UDS protocol simulation
* Watchdog timer integration

---

## 🏁 Conclusion

This project demonstrates a **real-world automotive communication model**, where multiple ECUs interact over CAN to build a reliable and scalable dashboard system. It provides a strong foundation for advanced automotive and embedded system development.


