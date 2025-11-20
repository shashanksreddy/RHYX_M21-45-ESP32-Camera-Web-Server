ESP32-CAM Video Streaming Web Server

A simple, lightweight video streaming web server for the AI-Thinker ESP32-CAM module. This project creates a standalone web page that streams MJPEG video directly from the ESP32.

Features

Instant Streaming: MJPEG video stream accessible via web browser.

Self-Contained: HTML and CSS are embedded in the code (no SPIFFS upload required).

Simple Interface: Clean, dark-themed web UI.

Hardware Required

ESP32-CAM Board (AI-Thinker Model recommended)

FTDI Programmer (USB-to-TTL) for uploading code

5V Power Supply

Software Requirements

Arduino IDE (1.8.x or 2.x)

ESP32 Board Manager installed in Arduino IDE

Setup & Installation

Clone the Repository:

git clone [https://github.com/YOUR_USERNAME/ESP32-CAM-WebServer.git](https://github.com/YOUR_USERNAME/ESP32-CAM-WebServer.git)


Open the Project:
Open CameraWebServer.ino in the Arduino IDE.

Configure WiFi:
Edit CameraWebServer.ino and enter your WiFi credentials:

const char *ssid = "YOUR_WIFI_NAME";
const char *password = "YOUR_WIFI_PASSWORD";


Board Settings:

Board: AI Thinker ESP32-CAM

CPU Frequency: 240MHz (WiFi/BT)

Flash Frequency: 80MHz

PSRAM: Enabled

Upload:

Connect GPIO 0 to GND.

Press the Reset button on the ESP32-CAM.

Click Upload in Arduino IDE.

Once uploaded, remove the connection between GPIO 0 and GND.

Usage

Open the Serial Monitor (baud rate 115200).

Press the Reset button on the ESP32-CAM.

The Serial Monitor will display an IP address (e.g., http://192.168.1.100).

Enter that IP address in your web browser.

Click Start Stream (or view the stream directly).

License

This project is licensed under the MIT License - see the LICENSE file for details.