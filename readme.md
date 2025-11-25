# Rhynx M21-45 & Standard OV2640 ESP32-CAM Video Server

![License](https://img.shields.io/badge/license-MIT-blue.svg)
![Platform](https://img.shields.io/badge/platform-ESP32-orange.svg)
![Arduino](https://img.shields.io/badge/framework-Arduino-00979D.svg)

A streamlined, lightweight video streaming server for **AI-Thinker ESP32-CAM** . Specifically verified for the Rhynx M21-45 (Black Ribbon) module, but also fully compatible with the standard OV2640 (Gold/Orange Ribbon) cameras.

## 📖 Description

This project provides a robust and simplified solution for streaming video from the ESP32-CAM. It is designed to solve the confusion between the two most common camera modules found in the wild:
* The Rhynx M21-45: Identifiable by its black ribbon cable and often obscure driver requirements. Many standard examples fail to work correctly with this specific batch.
* The Standard OV2640: Identifiable by its gold or orange ribbon cable. This is the classic module most tutorials expect.

While the standard ESP32 Camera examples are powerful, they are often bloated with complex features like face recognition and use compressed, unreadable HTML files that are difficult for beginners to modify. This repository solves that by stripping away the unnecessary complexity to provide a pure, low-latency video streaming server that "just works" for both camera types.

## ❓ Why You Should Use This Library

If you have bought an ESP32-CAM recently, you might have received the "Black Strip" Rhynx version without realizing it requires specific consideration. This project is plug-and-play for your hardware, regardless of which camera version you received. Furthermore, if you want to customize the web interface (add buttons, change colors, or embed it in another site), this library makes it incredibly easy because the HTML is standard, readable code right inside the sketch.

## Key Differences (Compared to Standard Library)

### 1. Solves the Camera Model Confusion
* **Standard Library:** Often defaults to settings that may not initialize the Rhynx M21-45 correctly.
* **This Project:** Explicitly supports both major variants (Rhynx M21-45 & Standard OV2640).

### 2. No More "Hex" HTML
* **Standard Library:** The web page is stored as a massive, unreadable array of hexadecimal numbers (Gzipped) inside `camera_index.h`.
* **This Project:** The website is stored as a **simple, plain text HTML string** inside `app_httpd.cpp`. You can edit it instantly.

### 3. Removed "Bloatware"
* **Standard Library:** Includes Face Detection/Recognition features that consume memory and lower frame rates.
* **This Project:** Pure MJPEG streamer for faster compilation and better stability.

### 4. Pre-Configured Pin Definitions
* **This Project:** The `camera_pins.h` file is pre-configured specifically for the AI-Thinker layout used by these modules.

## 📸 Hardware Compatibility
Specific Support:
Board: AI-Thinker ESP32-CAM (Generic)
Camera: Rhynx M21-45 (OV2640 2MP)
Identifier: Black ribbon cable with "Rhynx M21-45" text.

Note:This module often requires specific register settings which are handled by the standard library, but this codebase is verified to work with it.This is the version often identified by the "Rhynx M21-45" text printed on the black camera ribbon cable. While designed for the Rhynx M21-45, this code should also work with standard OV2640 camera modules commonly found on AI-Thinker boards.

## Module Differences: Rhynx vs. Standard OV2640

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

## ✨ Features

* **Instant Streaming:** MJPEG video stream accessible via web browser.
* **Self-Contained:** HTML and CSS are embedded in the code (no SPIFFS upload required).
* **Simple Interface:** Clean, dark-themed web UI.

## 🛠️ Hardware Required

* **ESP32-CAM Board**
* **FTDI Programmer** (USB-to-TTL) for uploading code
* **5V Power Supply**
* Jumper wires

💻 Software Requirements

* **Arduino IDE** (1.8.x or 2.x)
* **ESP32 Board Manager** installed in Arduino IDE

## ⚙️ Setup & Installation

### 1. Clone the Repository
bash
 git clone

### 2.Open CameraWebServer.ino in the Arduino IDE. Edit the WiFi credentials section:
* const char *ssid = "YOUR_WIFI_NAME";
* const char *password = "YOUR_WIFI_PASSWORD";

3. Board Settings (Arduino IDE)

Ensure your Tools menu is configured as follows:
| Setting | Value |
| :--- | :--- |
| **Board** | **AI Thinker ESP32-CAM** |
| **CPU Frequency**| "**240MHz (WiFi/BT)**" |
| **Flash Frequency** | 80MHz | 
| **PSRAM** | Enabled | 

4. Uploading the Code

* Connect the FTDI programmer to the ESP32-CAM.
* Connect GPIO 0 to GND (This puts the board into flashing mode).
* Press the Reset button on the ESP32-CAM.
* Click Upload in the Arduino IDE.
* Important: Once uploaded, remove the connection between GPIO 0 and GND.

## 🚀 Usage

* Open the Serial Monitor in Arduino IDE.
* Set the baud rate to 115200.
* Press the Reset button on the ESP32-CAM.
* The Serial Monitor will display an IP address (e.g., http://192.168.1.100).
* Enter that IP address in your web browser.
* Click Start Stream (or view the stream directly depending on your browser).

This project is licensed under the MIT License - see the LICENSE file for details.
