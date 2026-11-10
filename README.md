# IoT-Based Server Room Monitoring System

**Pandit Deendayal Energy University (PDEU)**  
**Department of Information and Communication Technology**  
**Faculty Guide:** Dr. Aarti Solanki  
**Developed by:** Ayushi Maniar (23BIT189) and Tanisha Diyora (23BIT188)

## Project Overview

The **IoT-Based Server Room Monitoring System** is an ESP32-based embedded monitoring project that brings together environmental sensing, access monitoring, and automatic local alerts in one compact solution. The system collects temperature, humidity, gas/smoke-related readings, door status, and motion activity. It presents these readings on an OLED display and uses a red LED and buzzer to indicate alert conditions.

The project demonstrates a practical, cost-conscious approach to continuous server-room condition monitoring using easily available hardware and Arduino-based programming.

## Key Features

* **Temperature and humidity monitoring** using a DHT11 sensor
* **Gas/smoke-related sensing** using an MQ-2 module
* **Door-status monitoring** using a magnetic door sensor
* **Motion detection** using a PIR sensor
* **Live local display** on a 0.96-inch OLED screen
* **Visual and audible alerts** through a red LED and buzzer
* **Serial Monitor output** for inspecting sensor readings and system status
* **Expandable architecture** with provision for relay-controlled fan operation

## Project Highlights and Novelty

Instead of monitoring individual parameters separately, this project integrates **environmental monitoring and physical-access awareness** into a single ESP32 controller. Multiple sensor inputs are evaluated in a continuous monitoring cycle, with a unified OLED display and immediate local alert mechanism. The modular design also supports further enhancements, including Wi-Fi connectivity, remote dashboards, notifications, and automated cooling.

## Hardware Components

|Component|Purpose|
|-|-|
|ESP32 development board|Main controller for sensor processing and alert outputs|
|DHT11|Measures temperature and humidity|
|MQ-2 gas sensor|Provides smoke/combustible-gas-related analog response|
|PIR sensor|Detects movement|
|Magnetic door sensor|Monitors door open/closed state|
|SSD1306 OLED (0.96-inch, I2C)|Displays readings and monitoring status|
|Red LED|Visual alert|
|Buzzer|Audible alert|
|Breadboard and jumper wires|Circuit assembly and connections|
|Relay and DC fan (optional)|Extension for temperature-based cooling|

## Circuit Connections

The following configuration follows the wiring plan documented in the project report.

|Component signal|ESP32 connection|
|-|-|
|MQ-2 analog output|GPIO 34 (through appropriate voltage scaling)|
|DHT11 data|GPIO 4|
|PIR output|GPIO 26|
|Magnetic door sensor|GPIO 27|
|OLED SDA|GPIO 21|
|OLED SCL|GPIO 22|
|Red LED|GPIO 19 (with current-limiting resistor)|
|Buzzer|GPIO 18 (with driver where required)|
|Optional relay input|GPIO 25|

Use module-appropriate power supplies and a common ground. ESP32 input signals must stay within their permitted voltage range; in particular, the MQ-2 analog signal may require a voltage divider.

## Software and Libraries

* Arduino IDE and ESP32 board support package
* Embedded C/C++
* Adafruit GFX Library
* Adafruit SSD1306 Library
* Adafruit DHT Sensor Library
* Adafruit Unified Sensor Library
* Wire library for I2C communication

## How the System Works

1. The ESP32 initializes the sensor interfaces, OLED display, and output pins.
2. The MQ-2, DHT11, magnetic door sensor, and PIR sensor provide their readings or states.
3. The program evaluates the inputs against configured monitoring conditions.
4. The OLED displays the latest environmental readings and access status.
5. The red LED and buzzer indicate an alert whenever a configured condition is triggered.
6. The monitoring cycle continues, updating the displayed information and outputs.

The report documents a **35°C high-temperature alert threshold**. Gas-sensor thresholds and input logic can be adjusted for the hardware setup.

## Running the Arduino Project

1. Install **Arduino IDE** and add ESP32 board support.
2. Install the Adafruit GFX, SSD1306, DHT, and Unified Sensor libraries.
3. Open `ServerRoomMonitoring.ino` in Arduino IDE.
4. Connect the components according to the circuit plan and the ratings of the modules.
5. Select the appropriate ESP32 board and COM/USB port.
6. Compile and upload the sketch.
7. Open the Serial Monitor at **115200 baud** and view the readings on both the monitor and OLED.
8. Demonstrate the door, motion, temperature, and alert functions with the connected hardware.

## Project Structure

```text
IoT-Server-Room-Monitoring/
├── ServerRoomMonitoring.ino    # ESP32 Arduino program
└── README.md                   # Project documentation
```

## Applications

* Educational server-room monitoring prototype
* Embedded sensor-integration demonstration
* Environmental and access-status monitoring
* Foundation for expanded smart facility monitoring systems

## Team Contributions

**Ayushi Maniar (23BIT189)** — Circuit design, hardware connections, component integration, and project report preparation.

**Tanisha Diyora (23BIT188)** — ESP32 program implementation, sensor-reading and alert logic, OLED display functionality, and project report preparation.

## Future Scope

* Wi-Fi connectivity for remote monitoring
* Cloud-based sensor data storage
* Browser dashboard and historical analytics
* Mobile alert notifications
* Improved sensor accuracy and automatic cooling integration

\---

**Academic Project | Pandit Deendayal Energy University (PDEU)**

