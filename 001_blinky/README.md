Project Overview

This project demonstrates controlling an external LED connected to GPIO2 of an ESP32-WROOM-32 board using Zephyr RTOS.

The project uses a Devicetree overlay to define the LED and reuses Zephyr's standard Blinky sample application.


Hardware Setup
GPIO2
  │
220Ω Resistor
  │
LED Anode (+)
LED Cathode (-)
  │
GND

Learnings
Zephyr Installation

Created Python virtual environment:
python3 -m venv .venv
source .venv/bin/activate

Installed:
west
Zephyr SDK

Build Process:
west build -p always \
-b esp32_devkitc/esp32/procpu \
samples/basic/blinky

Build flow:
Application
+
Devicetree
+
Zephyr Kernel
+
ESP32 BSP
+
Xtensa Toolchain
=
Firmware Image

Flashing:
west flash

Flashing flow:
west
 ↓
esptool
 ↓
UART
 ↓
ESP32 ROM Bootloader
 ↓
SPI Flash

Viewing Logs
screen /dev/ttyUSB0 115200


****************************************************
Devicetree Overlay

Added external LED definition:
aliases {
    led0 = &user_led;
};
This allows the Blinky sample to remain board-independent.
****************************************************
