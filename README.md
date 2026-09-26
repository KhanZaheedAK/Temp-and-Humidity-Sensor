# 🌡️ Temperature & Humidity Sensor — Arduino + 16×2 LCD

## 📌 Project Overview

This project uses a **DHT11 Temperature & Humidity Sensor** with an **Arduino** and a **16×2 I2C LCD** to measure the surrounding temperature and humidity and display the readings in real time.

This is **Episode 05 — Part 2** of the Robotics With ZK Sensor Series 1.0.

---

## 🧰 Components Required

* Arduino UNO
* DHT11 Temperature & Humidity Sensor
* 16×2 I2C LCD
* Jumper Wires
* Breadboard
* USB Cable

---

## 🔌 Connections

### DHT11 → Arduino UNO

* VCC → 5V
* GND → GND
* DATA → D2

### 16×2 I2C LCD → Arduino UNO

* VCC → 5V
* GND → GND
* SDA → A4
* SCL → A5

---

## ⚙️ How It Works

1. The **DHT11 sensor** measures temperature and humidity.
2. The sensor sends the readings to the **Arduino**.
3. Arduino processes the received data.
4. The readings are displayed on the **16×2 I2C LCD**.
5. The display continuously shows both temperature and humidity.

### 🔄 Working Flow

**DHT11 Sensor → Arduino UNO → 16×2 I2C LCD → Real-Time Readings**

---

## 📚 Libraries Required

Install these libraries through the Arduino IDE Library Manager:

* **DHT sensor library** — Adafruit
* **Adafruit Unified Sensor**
* **LiquidCrystal I2C**

---

## 🎯 Project Output

The LCD displays the measured values:

```text
Temp: 27.0°C
Hum:  60.0%
```

The values will vary depending on the surrounding environment.

---

## 🚀 Learning Outcomes

Through this project, you learn:

* How a DHT11 sensor works
* Reading sensor data with Arduino
* Using an I2C LCD
* Displaying real-time sensor values
* Basic sensor-to-display communication


---

## 🎥 Robotics With ZK

**Episode 05 — Part 2**
**Sensor Series 1.0**

Built and documented by **Robotics With ZK** 🤖
