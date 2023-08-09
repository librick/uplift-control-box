# Uplift Control Box Reverse Engineering
Schematics for the Uplift Desk V2 Commercial 2-Leg 120V Control Box.

MCU board with relays and accelerometer board removed:
![MCU board with relays and accelerometer board removed](./control-box-mcu-board.png)

## Motivation
I wanted to understand how my standing desk worked. I also wanted the schematics so that, if desired, I could replace the obscure microcontroller with a more developer-friendly alternative, such as something from the ESP32 family.

## Overview
Uplift desks use two linear actuators. Each linear actuator assembly uses a 6-pin AUX connector.
Two pins drive the motor itself; direction depends on the polarity of the applied voltage.
The voltage signals are PWM'd by the microcontroller to keep the linear actuators in sync.
Two of the pins are outputs from a quadrature encoder built into each leg assembly.
The encoders track the offset of the desk from the desk's lowest height (this is explains why resetting the desk involves fully lowering the desk).
Finally, there is a +5V pin to drive the quadrature encoder and a pin for ground.

The schematics provided are only for part of the control box.
The control box consists of two boards; these schematics are for the board that holds the microcontroller.
The other board has all the high-voltage transformers and supplies a +33V rail.

## Datasheets
This is the closest datasheet I could find for the microcontroller: https://www.nxp.com/docs/en/data-sheet/MC9S08PA16_Rev.1.pdf
It's not an exact match but appears to be pin-compatible.

## Copyright and License
I am not affiliated with Uplift Desk. All trademarks and IP are theirs.
Everything else is GPL2.
For more info on open source hardware licenses, see https://wiki.opensourceecology.org/wiki/Open_Source_Hardware_License.

