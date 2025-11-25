# ESP32-CAM Video Streaming Web Server

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Platform](https://img.shields.io/badge/platform-ESP32-orange.svg)
![Arduino](https://img.shields.io/badge/framework-Arduino-00979D.svg)

ESP32-CAM Video Streaming Web Server
A simple, lightweight video streaming web server for the **AI-Thinker ESP32-CAM** module. This project creates a standalone web page that streams MJPEG video directly from the ESP32 to your browser.

📸 Hardware Compatibility
Specific Support:
Board: AI-Thinker ESP32-CAM (Generic)
Camera: Rhynx M21-45 (OV2640 2MP)
Identifier: Black ribbon cable with "Rhynx M21-45" text.

Note:This module often requires specific register settings which are handled by the standard library, but this codebase is verified to work with it.This is the version often identified by the "Rhynx M21-45" text printed on the black camera ribbon cable. While designed for the Rhynx M21-45, this code should also work with standard OV2640 camera modules commonly found on AI-Thinker boards.

### Module Differences: Rhynx vs. Standard OV2640

While this project is designed for the Rhynx M21-45, it is also compatible with standard OV2640 modules.

| Feature | Rhynx M21-45 (This Project) | Standard OV2640 |
| :--- | :--- | :--- |
| **Ribbon Color** | **Black** | Orange / Gold |
| **Text on Ribbon**| "**Rhynx M21-45**" | "OV2640" |
| **Lens Type** | Standard | Standard |

#### Visual Comparison

<div align="center">
  <img src="images/rhynx.jpg" alt="Rhynx M21-45" width="45%">
  &nbsp; &nbsp; <img src="images/ov2640.jpg" alt="Standard OV2640" width="45%">
</div>

<p align="center">
  <em>Left: Rhynx M21-45 (Black Ribbon) | Right: Standard OV2640 (Orange/Gold Ribbon)</em>
</p>

✨ Features

* **Instant Streaming:** MJPEG video stream accessible via web browser.
* **Self-Contained:** HTML and CSS are embedded in the code (no SPIFFS upload required).
* **Simple Interface:** Clean, dark-themed web UI.

🛠️ Hardware Required

* **ESP32-CAM Board**
* **FTDI Programmer** (USB-to-TTL) for uploading code
* **5V Power Supply**
* Jumper wires

💻 Software Requirements

* **Arduino IDE** (1.8.x or 2.x)
* **ESP32 Board Manager** installed in Arduino IDE

⚙️ Setup & Installation

1. Clone the Repository
bash
git clone 
2.Open CameraWebServer.ino in the Arduino IDE. Edit the WiFi credentials section:
const char *ssid = "YOUR_WIFI_NAME";
const char *password = "YOUR_WIFI_PASSWORD";

3. Board Settings (Arduino IDE)

Ensure your Tools menu is configured as follows:

  Setting	            Value
Board	          ->   AI Thinker ESP32-CAM
CPU Frequency	  ->   240MHz (WiFi/BT)
Flash Frequency	->   80MHz
PSRAM	          ->   Enabled

4. Uploading the Code

->Connect the FTDI programmer to the ESP32-CAM.
->Connect GPIO 0 to GND (This puts the board into flashing mode).
->Press the Reset button on the ESP32-CAM.
->Click Upload in the Arduino IDE.
->Important: Once uploaded, remove the connection between GPIO 0 and GND.

🚀 Usage

->Open the Serial Monitor in Arduino IDE.
->Set the baud rate to 115200.
->Press the Reset button on the ESP32-CAM.
->The Serial Monitor will display an IP address (e.g., http://192.168.1.100).
->Enter that IP address in your web browser.
->Click Start Stream (or view the stream directly depending on your browser).

This project is licensed under the MIT License - see the LICENSE file for details.
