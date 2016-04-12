Port of the Adafruit BluefruitLE nRF51 library for Particle

A sample program is in firmware/examples/atcommand.ino. It allows you to type serial commands directly to the Bluefruit from the USB serial device.

For your own code, you will need to include these files:

#include "Adafruit_BLE/Adafruit_BLE.h"
#include "Adafruit_BLE/Adafruit_BluefruitLE_SPI.h"


You’ll also need to create an object to interface with the Bluefruit and assign pins:

Adafruit_BluefruitLE_SPI ble(&SPI, BLUEFRUIT_SPI_CS, BLUEFRUIT_SPI_IRQ, BLUEFRUIT_SPI_RST);


Sample connections as configured in the atcommand.ino sample file:

SCK - A3
MISO - A5
MOSI - A4
CS - A2 (can use any pin)
IRQ - D3 (can use any pin, does not use a hardware interrupt)
RST - D2 (can use any pin)
GND - GND
VIN - 3V3

You can use the SPI1 hardware SPI port if you prefer.



The latest version of this library for Particle here:
https://github.com/rickkas7/Adafruit_BLE

Original source:
https://github.com/adafruit/Adafruit_BluefruitLE_nRF51

Fork of the source for easy change merging is here:
https://github.com/rickkas7/Adafruit_BluefruitLE_nRF51



