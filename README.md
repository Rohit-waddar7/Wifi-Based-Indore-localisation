# WiFi-Based Indoor Positioning System

This project implements a basic indoor positioning system using RSSI (Received Signal Strength Indicator) values from multiple WiFi access points (APs). The ESP32 microcontroller scans for the signal strength of predefined APs and estimates the device's position based on a weighted RSSI method.

## Features
- Connects to a specified WiFi network.
- Scans for predefined access points and measures their RSSI values.
- Estimates the position of the device using a simple weighted RSSI-based approach.
- Outputs the estimated position to the Serial Monitor.
- ESP32 sends data serially to Qcar, and further commands will be given to the Qcar based on RSSI values and access points.

## Hardware Requirements
- ESP32 Development Board
- WiFi Network with at least four known access points
- Computer with Arduino IDE installed

## Software Requirements
- Arduino IDE
- ESP32 Board Package installed in Arduino IDE
- WiFi.h library (included in ESP32 core)

## Installation & Setup
1. **Clone this repository:**
   ```sh
   git clone https://github.com/yourusername/wifi-positioning.git
   cd wifi-positioning
   ```

2. **Open the project in Arduino IDE.**

3. **Modify the WiFi Credentials:**
   Edit the following lines in the `wifi_positioning.ino` file to match your network:
   ```cpp
   const char* ssid = "your_SSID";      // Replace with your Wi-Fi SSID
   const char* password = "your_PASSWORD";  // Replace with your Wi-Fi Password
   ```

4. **Modify Access Point Information:**
   Update the SSID names and coordinates of the access points:
   ```cpp
   const char* ap1 = "AP1_SSID";
   const char* ap2 = "AP2_SSID";
   const char* ap3 = "AP3_SSID";
   const char* ap4 = "AP4_SSID";
   
   float ap1_coords[2] = {0.0, 1.0};
   float ap2_coords[2] = {0.0, 0.0};
   float ap3_coords[2] = {1.0, 0.0};
   float ap4_coords[2] = {1.0, 1.0};
   ```

5. **Upload the code to ESP32:**
   - Connect ESP32 to your computer.
   - Select the correct board and port in Arduino IDE.
   - Click the upload button.

6. **Monitor Output:**
   - Open the Serial Monitor (115200 baud rate) in Arduino IDE.
   - View the estimated position updates in real-time.

## How It Works
1. The ESP32 connects to the specified WiFi network.
2. It scans for the predefined APs and collects their RSSI values.
3. If all APs are detected, the position is estimated using a weighted RSSI approach.
4. The estimated position is displayed in the Serial Monitor.

