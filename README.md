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

## 💻 Arduino Code

```cpp
#include <Wire.h>
#include <LiquidCrystal_I2C.h>
#include <DHT.h>

#define DHTPIN 2
#define DHTTYPE DHT11

DHT dht(DHTPIN, DHTTYPE);
LiquidCrystal_I2C lcd(0x27, 16, 2);

void setup() {
  dht.begin();

  lcd.init();
  lcd.backlight();

  lcd.setCursor(0, 0);
  lcd.print("Temp & Humidity");
  delay(2000);
  lcd.clear();
}

void loop() {
  float humidity = dht.readHumidity();
  float temperature = dht.readTemperature();

  if (isnan(humidity) || isnan(temperature)) {
    lcd.clear();
    lcd.setCursor(0, 0);
    lcd.print("Sensor Error!");
    delay(2000);
    return;
  }

  lcd.setCursor(0, 0);
  lcd.print("Temp: ");
  lcd.print(temperature, 1);
  lcd.print((char)223);
  lcd.print("C   ");

  lcd.setCursor(0, 1);
  lcd.print("Hum:  ");
  lcd.print(humidity, 1);
  lcd.print("%   ");

  delay(2000);
}
```

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

## 📂 Project Structure

```text
Temperature-Humidity-Sensor/
│
├── Temperature_Humidity_Sensor.ino
├── README.md
└── circuit/
    └── connections.txt
```

---

## 🎥 Robotics With ZK

**Episode 05 — Part 2**
**Sensor Series 1.0**

Built and documented by **Robotics With ZK** 🤖

#Arduino #Robotics #Electronics #Engineering #RoboticsWithZK
