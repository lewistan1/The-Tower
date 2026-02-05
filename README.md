🌈 MoodLamp – Wi-Fi Controlled Interactive LED & Servo Lamp

MoodLamp is a Wi-Fi–enabled interactive lighting system built using an ESP32, NeoPixel LED rings, servo motors, and an Android application.
It supports real-time colour control, brightness adjustment, rainbow animations, and physical touch interaction, making it suitable for interactive installations, educational demos, or creative ambient lighting projects.

✨ Features
Android App

Manual IP address input for ESP32

ON / OFF / Rainbow control

Brightness slider (0–255)

Master color picker to control all lights

Individual color control for each light

Adaptive button text colour (auto switches black/white for readability)

Live HTTP request & response log

ESP32 Firmware

Wi-Fi–based HTTP server (port 80)

Controls:

3 NeoPixel rings (24 LEDs each)

2 servo motors

Touch input for local control

Operating modes:

STATIC – solid colour with servo motion mapped to colour brightness

RAINBOW – smooth colour fading with organic servo motion

Touch controls:

Short press → cycle colours / modes

Long press (2s) → turn OFF + relax servos

Smooth servo motion with easing and randomised behaviour

🧠 System Architecture
Android App (HTTP GET)
        ↓
ESP32 Web Server (MicroPython)
        ↓
NeoPixel Rings + Servo Motors

🔌 Hardware Components
Component	Quantity
ESP32	1
NeoPixel LED Ring (24 LEDs)	3
Servo Motors	2
Touch Sensor / Touch Pin	1
External Power Supply	1
Pin Configuration
Function	ESP32 Pin
NeoPixel Ring 1	GPIO 5
NeoPixel Ring 2	GPIO 6
NeoPixel Ring 3	GPIO 7
Servo 1	GPIO 1
Servo 2	GPIO 2
Touch Input	GPIO 0
📱 Android App Controls
Control	Action
ON	Set first static colour
OFF	Turn off LEDs + stop servos
Rainbow	Start rainbow animation
Brightness	Adjust LED brightness
Master Color Picker	Set all lights
Light 1 / 2 / 3	Set individual colours
🌐 HTTP API (ESP32)
Endpoint	Description
/on	Turn on static mode
/off	Turn off all lights
/rainbow?state=on	Enable rainbow mode
/brightness?value=0–255	Set brightness
/color1?r=&g=&b=	Set light 1 colour
/color2?r=&g=&b=	Set light 2 colour
/color3?r=&g=&b=	Set light 3 colour
🖐 Touch Control Behaviour
Interaction	Action
Short press	Cycle colour / mode
Long press (≥2s)	Turn OFF + stop servos
🛠 Software Stack

ESP32: MicroPython

Android App: Java (Android Studio)

Networking: HTTP GET via OkHttp

LED Control: NeoPixel library

Servo Control: PWM (50 Hz)

🚀 Setup Instructions
ESP32

Flash MicroPython onto ESP32

Upload the firmware script

Update Wi-Fi SSID and password if needed

Power on ESP32 and note its IP address

Android App

Open project in Android Studio

Build & install APK

Enter ESP32 IP address

Start controlling the MoodLamp 🎨

📸 Demo & Screenshots

(Add photos or videos here)

🧪 Known Limitations

HTTP parsing is lightweight (no full header parsing)

Single client connection at a time

No persistent state storage on reboot

🌱 Future Improvements

REST-style JSON API

Preset save/load

Web UI fallback

ESP32 captive portal setup

Smoother LED gamma correction

👤 Author

Lionel Rafy
Singapore Polytechnic – FabLab / EEE
Interactive & Educational Prototyping Project
