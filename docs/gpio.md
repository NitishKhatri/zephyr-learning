Objective

Understand General Purpose Input Output pins and LED control.

What is GPIO?
GPIO stands for: General Purpose Input Output
A programmable digital pin.


Modes :
==> Output

Used to drive signals.

Example:
LED
Relay
Buzzer

==> Input
Used to read signals.
Example:
Button
Interrupt source
Switch


************************************************************************************************************************************************************************************************
GPIO in Zephyr
Application retrieves GPIO information from Devicetree: GPIO_DT_SPEC_GET(...) instead of hardcoding pin numbers.

************************************************************************************************************************************************************************************************
