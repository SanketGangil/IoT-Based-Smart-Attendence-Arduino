# IoT-Based Fingerprint Attendance System

This project is an IoT-enabled fingerprint attendance system built using an **ESP32**, **R307 fingerprint sensor**, and **Google Sheets integration** via Google Apps Script. The system verifies students using their fingerprint and automatically logs their attendance to a Google Sheet.

## 📌 Features

- 🔒 Secure fingerprint verification using Adafruit R307
- 📶 Real-time attendance logging via WiFi
- 📋 Integration with Google Sheets using Apps Script
- 📟 16x2 LCD for on-device feedback (status, name, roll number)
- 🚨 LED and buzzer indicators for success/failure
- 👨‍🎓 Stores multiple student records (ID, name, roll number)

## 📷 Hardware Used

- ESP32 Dev Module
- R307 Fingerprint Sensor
- LCD Display (16x2) with I2C Module
- Breadboard & Jumper Wires
- LEDs (Red, Blue)
- Buzzer

## 🔧 Software Used

- Arduino IDE
- ESP32 board packages
- Required libraries:
  - `Adafruit_Fingerprint`
  - `WiFi.h`
  - `HTTPClient.h`
  - `LiquidCrystal.h`

## 🚀 How It Works

1. The fingerprint sensor scans the finger and checks against registered templates.
2. On a successful match:
   - LCD shows student details.
   - Blue LED flashes.
   - Data is sent to Google Sheets via a Web App URL.
3. On failure:
   - LCD shows "Not Matched!"
   - Red LED and buzzer trigger.

## 📄 Setup Instructions

1. **Connect all hardware components** as per your pin definitions in the `.ino` file.
2. **Upload the code** using Arduino IDE.
3. **Create a Google Apps Script Web App**:
   - Create a new project.
   - Use Google Sheets script to log data.
   - Deploy as Web App and copy the URL.
4. **Replace `googleScriptURL`** in the code with your Web App URL.
5. **Power on ESP32**. You're good to go!

## 🧠 Student Record Format (in code)

```cpp
Student students[] = {
  { 1, "2022UEI6567", "Sumedha" },
  { 2, "2022UEI2838", "Kusagra Kumar" },
  ...
};
