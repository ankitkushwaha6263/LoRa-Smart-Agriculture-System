# LoRa-Smart-Agriculture-System
Long range IoT based smart irrigation system using ESP32 and LoRa (SX1278)
# 🌱 Advanced LoRa + IoT Smart Irrigation System

## 📌 Problem Statement

Traditional irrigation systems rely heavily on manual control or unstable internet-based solutions. In rural areas:

* ❌ Wi-Fi is unavailable
* ❌ Cellular networks are unreliable or costly
* ❌ Over-irrigation causes water wastage and crop damage

This creates a critical need for a **reliable, long-range, and fail-safe irrigation system**.

---

## 💡 Proposed Solution

This project implements a **hybrid smart irrigation system** using:

* 📡 LoRa (SX1278) → Long-range communication (10–15 km)
* 🌐 Wi-Fi (ESP32) → Cloud connectivity via Blynk
* ⚙️ Dual-Core Processing → Reliable real-time control

👉 The system works even **without internet at field level** and still allows **global monitoring via cloud**.

---

## 🧠 System Architecture

The system is divided into two main nodes:

### 📡 1. Field Node (Transmitter)

* Arduino Nano + Soil Moisture Sensor
* Reads analog moisture data (0–1023)
* Converts into percentage (0–100%)
* Sends data via LoRa

### 🌐 2. Control Node (Receiver + Gateway)

* ESP32 + LoRa + WiFi
* Receives field data
* Controls pump via relay
* Sends data to Blynk cloud

---

## ⚙️ Key Features

* 📡 Long-range communication up to 15 km 
* 🌱 Real-time soil moisture monitoring
* ⚡ Automatic irrigation using threshold logic
* 📱 Mobile control using Blynk IoT
* 🔁 Offline working even if internet fails 
* 🧠 Dual-core task separation using FreeRTOS

---

## 🔄 Working Principle

1. Soil sensor reads moisture value
2. Arduino converts it into percentage
3. Data sent via LoRa packet (`WET:value`) 
4. ESP32 receives and processes data
5. Decision logic:

   * If moisture < threshold → Pump ON
   * Else → Pump OFF
6. Data is also sent to Blynk cloud

---

## 🧩 Operating Modes

### 1. 🤖 Auto Mode

* Fully automatic irrigation based on moisture threshold

### 2. ⏱️ Timer Mode

* User sets irrigation time using buttons
* Works without internet

### 3. 📱 Cloud Mode

* Remote control via Blynk mobile app
* Global monitoring + manual override

---

## ⚠️ Challenges Faced

* 📡 Signal attenuation over long distance
* ⚡ EMI noise due to relay switching
* 🌐 Integration of LoRa with cloud system
* 🔁 Packet loss in wireless transmission

---

## 🛠️ Solutions Implemented

* Optimized antenna placement for better range
* Used **Chirp Spread Spectrum (CSS)** for noise resistance 
* Applied **decoupling capacitors & grounding**
* Implemented retry & validation logic
* Used ESP32 dual-core to prevent system crash

---

## 💻 Technologies Used

* Arduino Nano
* ESP32 (Dual-Core)
* LoRa Module (SX1278 - 433MHz)
* Blynk IoT Cloud
* Soil Moisture Sensor
* Relay Module
* Servo Motor + I2C LCD

---

## 📷 Project Image

![Project](images/project.jpg)

---

## 📽️ Demo Video

👉 [https://youtu.be/b9hg6W-bReo?si=VDYr_r88lYuf-TLs]

---

## 💻 Code Structure

* `/code/lora_tx.ino` → Transmitter
* `/code/lora_rx.ino` → Receiver + Blynk

---

## ✅ Results

* Achieved stable communication over long distances
* Fully automated irrigation system
* Reliable operation even during internet failure 
* Reduced water wastage and manual effort

---

## 🔮 Future Scope

* ☀️ Solar-powered field node
* 📊 Data analytics & prediction using ML 
* 🌦️ Weather API integration
* 🌐 LoRa mesh network for large farms

---

## ⭐ Conclusion

This project presents a **fault-tolerant, scalable, and real-world smart irrigation system** combining LoRa communication and IoT cloud technology, suitable for modern agriculture.

---
