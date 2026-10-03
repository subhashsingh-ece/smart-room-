# Smart Building Automation & Safety System 🏢

An ESP32-based Smart Building Automation and Safety System designed to improve energy efficiency, occupant experience, and room safety.

The system uses two PIR sensors to detect whether people are entering or leaving the room, automatically controls the lights based on the number of people inside, monitors gas and temperature, and controls a window using a servo motor.

## 🚀 Features

- 👥 Occupancy detection and people counting
- 💡 Automatic room light control
- 🚪 Entry and exit detection using two PIR sensors
- 🌡️ Temperature monitoring using DS18B20
- 🛑 Gas leakage detection
- 🪟 Automatic window control using servo motor
- 📟 Real-time OLED display
- ⚡ Energy-efficient room automation
- 🔧 ESP32-based control system

## 🔧 Components Used

- ESP32
- 2 × PIR Motion Sensors
- Gas Sensor
- DS18B20 Temperature Sensor
- Servo Motor
- OLED Display (I2C)
- 2 × LEDs
- 2 × 220Ω Resistors
- Breadboard
- Jumper Wires

## 🔌 Pin Connections

| Component | ESP32 Pin |
|-----------|-----------|
| PIR-A OUT | D27 |
| PIR-B OUT | D33 |
| Gas Sensor AO | D34 |
| DS18B20 DATA | D4 |
| Servo Signal | D13 |
| LED 1 | D25 |
| LED 2 | D26 |
| OLED SDA | D21 |
| OLED SCL | D22 |

### Power Connections

**PIR Sensors**
- VCC → 5V
- GND → GND

**Gas Sensor**
- VCC → 5V
- GND → GND
- AO → D34

**DS18B20**
- VCC → 3.3V
- GND → GND
- DATA → D4

**OLED**
- VCC → 3.3V
- GND → GND
- SDA → D21
- SCL → D22

**Servo Motor**
- Signal → D13
- VCC → External 5V
- GND → Common GND

**LED 1**
- D25 → 220Ω resistor → LED → GND        // it is replace by fan

**LED 2**
- D26 → 220Ω resistor → LED → GND

> ⚠️ If using a 5V gas sensor, make sure its analog output does not exceed the ESP32 ADC input limit of 3.3V. Use a voltage divider if required.

## 🧠 Working Principle

### 1. Occupancy Detection

Two PIR sensors are installed at the entrance of the room.

```text
OUTSIDE
   |
[PIR-A]
   |
 DOOR
   |
[PIR-B]
   |
 ROOM
