# Smart Firefighting RC Car with Bluetooth Telemetry

An Arduino-based robotic vehicle capable of remote navigation, localized flame detection, and targeted water-pump actuation, controlled wirelessly via an HC-05 Bluetooth module.

---

## 📸 Project Showcase

<p align="center">
  <img src="RC CAR/IMAGES/WhatsApp Image 2026-09-21 at 16.30.15.jpeg" width="350%" alt="Firefighting Car View 1" />
  <img src="RC CAR/IMAGES/WhatsApp Image 2026-09-21 at 16.30.13.jpeg" width="350%" alt="Firefighting Car View 2" />
</p>

---

## 🛠 Key Features
* **Wireless Control:** Full bi-directional command processing over Bluetooth Classic (HC-05) via UART at 9600 baud.
* **Flame Detection:** Sensor array monitoring infrared wavelength spikes to locate fire hazards.
* **Automated Fire Suppression:** Micro-submersible water pump driven via switching transistor/relay logic when fire is detected.
* **Failsafe Watchdog:** Non-blocking elapsed-time tracking (`millis()`) that automatically cuts motor power if the wireless connection drops.

---

## 🔌 Hardware Architecture
| Component | Function | Interface / Logic |
| :--- | :--- | :--- |
| **Arduino Uno / Nano** | Main control microcontroller | 5V TTL |
| **HC-05 Module** | Bluetooth wireless telemetry | UART (TX/RX) |
| **L293D Driver** | Dual H-Bridge motor propulsion | Digital GPIO + PWM |
| **Flame Sensor Module** | IR flame radiation detection | Digital / Analog Input |
| **DC Water Pump + Relay/Transistor** | Fire extinguishing mechanism | Digital GPIO Switch |
| **Servo Motor** | Water nozzle / Steering actuation | 50 Hz PWM |

---

## 💻 Firmware
* The main firmware is located in the [`RC CAR/Code/`](RC CAR/Code/Code.ino) directory.
* Uses non-blocking timing routines to ensure responsive control loops without halting execution.
