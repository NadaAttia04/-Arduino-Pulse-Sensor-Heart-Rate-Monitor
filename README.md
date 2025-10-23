# ❤️ Arduino Pulse Sensor – Heart Rate Monitor
A simple Arduino-based project that uses a pulse sensor to measure and display real-time heart rate (BPM) on a 16×2 LCD screen.   This project demonstrates how to interface a pulse sensor with Arduino, process heartbeat data, and visualize results in an interactive and educational way.

---

## 📑 Table of Contents
1. [Project Overview](#project-overview)  
2. [Components List](#components-list)  
3. [Schematics / Circuit Diagram](#schematics--circuit-diagram)  
4. [Code Explanation](#code-explanation)  
5. [Setup Instructions](#setup-instructions)  
6. [Usage Instructions](#usage-instructions)  
7. [Source Code / Program](#source-code--program)  
8. [Results / Expected Behavior](#resultsexpected-behavior)  
9. [Troubleshooting](#troubleshooting)

---

## 🧠 Project Overview
This project uses a **pulse sensor** with an **Arduino** to measure heart rate.  
The sensor detects heartbeats by analyzing changes in light when a finger is placed on it.  
The Arduino processes this data and displays the heart rate on a **16×2 LCD screen**.  

It’s a simple and effective way to create a real-time **heart rate monitor** using basic components and Arduino programming.

---

## ⚙️ Components List
1. Arduino UNO Board  
2. Pulse Sensor  
3. 16×2 I2C LCD Display  
4. Jumper Wires  
5. Breadboard  

---

## 🔌 Schematics / Circuit Diagram
<img width="1117" height="487" alt="image" src="https://github.com/user-attachments/assets/c0f476e5-bda5-4b1b-bbe2-a723681643c6" />

---

## 💻 Code Explanation

This Arduino code interfaces a pulse sensor with a 16x2 LCD screen to create a **heart rate monitor**.

### 1️⃣ Library Inclusion
- Includes the following libraries:  
  - `PulseSensorPlayground.h` → for pulse sensor interface  
  - `LiquidCrystal_I2C.h` → for controlling the LCD screen

### 2️⃣ Initialization
- Defines the LCD address (`0x27`) and its dimensions (`16x2`).  
- Declares constants for:
  - Pulse sensor pin  
  - LED pin  
  - Threshold value for detecting heartbeats  
- Creates an instance of `PulseSensorPlayground`.

### 3️⃣ Setup Function
- Initializes **Serial communication** for debugging.  
- Initializes and turns on the **LCD screen**.  
- Configures the **pulse sensor**:  
  - Specifies the analog pin connection.  
  - Sets onboard LED to blink with each heartbeat.  
  - Sets the threshold for detecting beats.  
- Prints initialization status to the Serial Monitor.
<img width="1125" height="818" alt="image" src="https://github.com/user-attachments/assets/e32c733b-5541-4329-82cf-b0b7f68ded2e" />

### 4️⃣ Loop Function
- Displays **"Heart Rate"** on the first line of the LCD.  
- Reads the current **BPM value** from the pulse sensor.  
- If a heartbeat is detected (`sawStartOfBeat()`):  
  - Prints BPM to the Serial Monitor.  
  - Updates the LCD display.  
- Adds a short delay for stability and reduced CPU usage.

---

## ⚙️ Setup Instructions
- **VCC (Power):** Connect I2C LCD `VCC` → Arduino `5V`  
- **GND (Ground):** Connect I2C LCD `GND` → Arduino `GND`  
- **SCL (Clock):** Connect I2C LCD `SCL` → Arduino `A5`  
- **SDA (Data):** Connect I2C LCD `SDA` → Arduino `A4`

---

## 🩸 Usage Instructions
The **Pulse Sensor** works on the principle of **Photoplethysmography (PPG)** — a non-invasive method for measuring changes in blood volume under the skin.
<img width="1064" height="375" alt="image" src="https://github.com/user-attachments/assets/90e1545f-a32f-4404-80fc-d4d6f8dd507b" />

### Working Principle:
1. 💡 **Light Emission:** A green LED emits light into the skin.  
2. 🔁 **Reflection & Detection:** The light interacts with blood and reflects back to a photodetector.  
3. ❤️ **Heart Rate Detection:** Changes in reflected light form a waveform corresponding to heartbeats.  
4. 🌬️ **Oxygen Level:** Reflected light also relates to oxygen saturation (oxygenated blood absorbs more green light).  
5. 🔉 **Signal Filtering:** A Low-Pass Filter removes noise from the raw signal.  
6. ⚡ **Amplification:** An operational amplifier strengthens the filtered signal.  
7. 🧮 **Data Reading:** Arduino reads the signal and converts it into BPM and (optionally) oxygen level.

---

## 💾 Source Code / Program
<img width="1125" height="562" alt="image" src="https://github.com/user-attachments/assets/65357e3d-70ba-4db0-b73d-6fc640842fc8" />
<img width="1125" height="378" alt="image" src="https://github.com/user-attachments/assets/3629a54b-c381-4f51-9f83-38d1e0c876a7" />

## 📊 Results / Expected Behavior
<img width="1044" height="364" alt="image" src="https://github.com/user-attachments/assets/91aa1fd9-1dec-4923-81fc-63724c5a160d" />

- ✅ Upload the sketch to your **Arduino board**.  
- 🩸 Place your **finger on the Pulse Sensor**.  
- 💓 The **BPM value** will be displayed on the **LCD screen**.
- <img width="1079" height="458" alt="image" src="https://github.com/user-attachments/assets/c48951fc-024d-4ea1-b089-810a0861261e" />

- ✋ Keep your finger **steady** to get stable and accurate readings.  
- ⏱️ Initial readings may **fluctuate** — wait a few seconds for consistent results.  

---

## 🧩 Troubleshooting

- ⚡ **Check Operating Voltage:** Ensure the sensor runs between **3.3V–5.5V**.  
- 🖐️ **Secure the Sensor:** Use tape to fix it to your finger for more stable readings.
- <img width="1026" height="438" alt="image" src="https://github.com/user-attachments/assets/e0c439cb-bb91-4694-b57a-b7d3d1510594" />

- ⏳ **Be Patient:** Allow a few seconds for stable output.  
- 💡 **Avoid External Light:** Shield the sensor from ambient light to avoid interference.  
- 🔉 **Use a Low-Pass Filter:** Add a software-based filter in your code if readings are noisy.  

---

## 🧑‍💻 Author

- **Nada Attia** → [GitHub Profile](https://github.com/NadaAttia04)  
- **Farida Ayman** → [GitHub Profile](https://github.com/FaridaAyman)  
- **Rodina Ahmed** → [GitHub Profile](https://github.com/RodinaAhmed)

---

⭐ *If you like this project, don't forget to star the repository!*

---
