# Flux.ai Wiring Guide

Here's a basic guide to wiring your components. Please note that the exact pins may vary depending on the specific products you have, and you should always check the datasheets or product pages for your specific components to ensure correct connections. This guide assumes you're using an Arduino Pro Mini, a Nema 17HS4401S stepper motor with a 4-wire connection, an A4988 stepper motor driver, a KY-040 rotary encoder, and a 1602 LCD with I2C converter.

Nema 17HS4401S Stepper Motor to A4988 Stepper Motor Driver:

Connect the two coils of the stepper motor to the A4988 driver. The order is important and it depends on the wire color of your stepper motor. A possible order is: Coil1 (Black, Green), Coil2 (Red, Blue).

Black -> 2B

Green -> 2A

Red -> 1A

Blue -> 1B


A4988 Stepper Motor Driver to Arduino Pro Mini:

Connect the following pins:

DIR -> Digital Pin (Choose a digital pin on the Arduino, e.g., 2)

STEP -> Digital Pin (Choose a different digital pin on the Arduino, e.g., 3)

GND -> GND

VDD -> VCC (5V)


Power to A4988 Stepper Motor Driver:

Connect your 12V power supply to VMOT and GND on the A4988. Make sure your power supply is off when making these connections.


Rotary Encoder (KY-040) to Arduino Pro Mini:

Connect the following pins:

CLK (sometimes labeled A or OUTA) -> Digital Pin (e.g., 4)

DT (sometimes labeled B or OUTB) -> Digital Pin (e.g., 5)

SW (Switch) -> Digital Pin (e.g., 6)

'+' (sometimes labeled VCC) -> VCC

GND -> GND


1602 LCD with I2C Converter to Arduino Pro Mini:

Connect the following pins:

GND -> GND

VCC -> VCC (5V)

SDA -> A4

SCL -> A5


DC-DC Converter:

This can be used to provide power to your Arduino if your power supply voltage is higher than the Arduino can handle. For example, if you have a 12V power supply, you can use the DC-DC converter to step down the voltage to a level safe for the Arduino (5V). Connect the input of the converter to your power supply, and the output to the RAW (or VIN) and GND pins on your Arduino.


This is a basic wiring guide and does not include any additional components like capacitors that might be required for decoupling or smoothing voltage. Always consult the datasheets and be aware of the power requirements and limitations of your components.

