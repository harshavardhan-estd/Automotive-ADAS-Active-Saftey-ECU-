# Automotive-ADAS-Active-Saftey-ECU-
An embedded Advanced Driver Assistance System (ADAS) ECU developed on an STM32 ARM Cortex-M microcontroller. Integrates ultrasonic distance measurement, dual-IR lane departure tracking, asynchronous ambient light sensing via hardware external interrupts (EXTI), and real-time SSD1306 OLED telemetry.
# STM32 Automotive ADAS & Active Safety ECU

An embedded Advanced Driver Assistance System (ADAS) ECU prototype developed on an STM32 ARM Cortex-M microcontroller. The system handles real-time proximity detection, lane departure tracking, ambient light sensing via external interrupts (EXTI), and real-time OLED telemetry rendering.

## 📌 Key Features

* **Proximity Detection & Audio Warnings:** HC-SR04 ultrasonic sensor integration with dynamic PWM audio pitch scaling (800 Hz – 2000 Hz) based on collision risk distance thresholds.
* **Lane Departure Monitoring:** Dual infrared (IR) sensors configured for lane boundary tracking and drift alert triggering.
* **Interrupt-Driven Auto-Headlights:** Asynchronous ambient light detection using an LDR module coupled to an STM32 External Interrupt (EXTI) line on pin `PA4`.
* **Live Telemetry UI:** High-contrast 128x64 SSD1306 I2C OLED display refreshing system health, sensor readings, and warnings at 10 Hz.

---

## 🛠️ Hardware Specifications & Pinout

| Peripheral / Component | STM32 Pin | Interface / Protocol | Function |
| :--- | :--- | :--- | :--- |
| **HC-SR04 Trigger** | `PA0` | GPIO Output | Ultrasonic Trigger Pulse |
| **HC-SR04 Echo** | `PA1` | GPIO Input | Pulse Width Timing |
| **IR Sensor (Left)** | `PA2` | Digital Input | Lane Boundary Tracking |
| **IR Sensor (Right)** | `PA3` | Digital Input | Lane Boundary Tracking |
| **LDR Sensor** | `PA4` | EXTI Interrupt | Ambient Light Threshold |
| **Active Buzzer** | `PA8` | PWM / Tone Output | Variable Pitch Alert |
| **Status LED / Light** | `PC13` | GPIO Output (Active LOW) | Headlight Indicator |
| **SSD1306 OLED** | `PB6 / PB7` | I2C (Address: `0x3C`) | Telemetry Display |

---

## 💻 Tech Stack & Tools

* **Target Microcontroller:** STM32 (ARM Cortex-M core)
* **Framework:** Arduino Core for STM32 / PlatformIO
* **Languages:** Embedded C / C++
* **Libraries:** `Adafruit_SSD1306`, `Adafruit_GFX`, `Wire`
* **Development Environment:** VS Code with PlatformIO IDE

---

## 🚀 Build and Flash Instructions

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/harshavardhan-estd/Automotive-ADAS-Active-Safety-ECU-STM32.git
   cd Automotive-ADAS-Active-Safety-ECU-STM32
   ```
