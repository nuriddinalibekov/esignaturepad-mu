Project Title: E-Signature Drawing Pad\n
Module: Programming Internet of Things
University: Millat Umidi University (MU)
Lecturer: Lazizbek Yusupov
Semester: Fall 2025

A real-time touchscreen drawing application built using ESP8266 and a TFT display with touch support.
The project allows smooth, fast, freehand drawing directly on the display with thick, continuous lines and minimal lag.

Designed with performance and responsiveness in mind.

✨ Features

Real-time freehand drawing

Smooth and thick strokes using drawWideLine()

Touch-based UI buttons

Clear canvas

Stable drawing area with calibrated touch mapping

Modular and readable code

Runs fully on-device (no PC required)

🧰 Hardware Requirements

ESP8266 (NodeMCU / ESP-12 / ESP8266 Dev Board)

TFT display with resistive touch
(e.g. ILI9341 + XPT2046)

Jumper wires

USB or external power supply

📦 Software & Libraries

Arduino IDE

ESP8266 Board Package

TFT_eSPI library

Make sure User_Setup.h in TFT_eSPI is configured correctly for your display and touch controller.

⚙️ How It Works

Touch coordinates are read from the touchscreen controller.

Consecutive points are connected using drawWideLine() for thick strokes.

Drawing is limited to a defined canvas area.

Touch release resets the drawing state to avoid artifacts.

No heavy filtering or delays are used to preserve speed.

This approach ensures continuous drawing even at high finger speed.

🧪 Calibration

Touch calibration values are applied directly in code to map raw touch input to screen coordinates.

If using a different display or controller, recalibration may be required.

Wiring 

LCD Pin   |	Connect to ESP32 | Description
VCC       |	5V	             | Power supply
GND	      | GND              | Ground
CS	      | GPIO 15	         | Chip select for display
RESET	    | GPIO 4           | Reset pin
DC (RS)	  | GPIO 2	         | Data/command select
SDI (MOSI)|	GPIO 23	         | SPI data to display
SDO (MISO)|	GPIO 19	         | SPI data from display
SCK       | GPIO 18	         | SPI clock
T_CS    	| GPIO 14	         | Touch chip select
T_IRQ     |	GPIO 27          | Touch interrupt (optional)
