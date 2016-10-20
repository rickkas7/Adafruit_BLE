# Port of the Adafruit BluefruitLE nRF51 library for Particle

A sample program is in firmware/examples/atcommand.ino. It allows you to type serial commands directly to the Bluefruit from the USB serial device.

## SPI

This code works with the [Adafruit Bluefruit LE SPI Friend] (https://www.adafruit.com/products/2633).

For your own code, you will need to include these files:

```
#include "Adafruit_BLE/Adafruit_BLE.h"
#include "Adafruit_BLE/Adafruit_BluefruitLE_SPI.h"
```

You’ll also need to create an object to interface with the Bluefruit and assign pins:

```
Adafruit_BluefruitLE_SPI ble(&SPI, BLUEFRUIT_SPI_CS, BLUEFRUIT_SPI_IRQ, BLUEFRUIT_SPI_RST);
```

Sample connections as configured in the atcommand.ino sample file:

* SCK - A3
* MISO - A5
* MOSI - A4
* CS - A2 (can use any pin)
* IRQ - D3 (can use any pin, does not use a hardware interrupt)
* RST - D2 (can use any pin)
* GND - GND
* VIN - 3V3

You can use the SPI1 hardware SPI port if you prefer.

## UART (Serial)

The software can also be used with the [Adafruit Bluefruit LE UART Friend] (https://www.adafruit.com/products/2479). 

```
#include "Adafruit_BLE/Adafruit_BLE.h"
#include "Adafruit_BLE/Adafruit_BluefruitLE_UART.h"
```

```	
// Optional, set to -1 her and leave MODE unconnected if not using
#define BLUEFRUIT_UART_MODE_PIN	 	   -1 

Adafruit_BluefruitLE_UART ble(&Serial1, BLUEFRUIT_UART_MODE_PIN);
```

Connections:

* MOD - Optional for changing between modes (see note below)
* CTS - Must connect to GND!
* TXD - Connect to Photon/Electron RX pin
* RXI - Connect to Photon/Electron TX pin
* VIN - Connect to 3V3
* RTS - No connection
* GND - Connect to GND
* DFU - No connection

The Adafruit board has a switch that choose between CMD and UART mode. You can also control this through software by connecting the MOD pin to a output. Specify the pin wit `BLUEFRUIT_UART_MODE_PIN`.

On the Particle Electron, you can also use Serial4 (TX=C3, RX=C2) or Serial5 (TX=C1, RX=C0).


## Other resources

Adafruit Project: 
[https://learn.adafruit.com/introducing-the-adafruit-bluefruit-spi-breakout/introduction] (https://learn.adafruit.com/introducing-the-adafruit-bluefruit-spi-breakout/introduction)

The latest version of this library for Particle here: 
[https://github.com/rickkas7/Adafruit_BLE] (https://github.com/rickkas7/Adafruit_BLE)

Original source including additional example programs (not ported): 
[https://github.com/adafruit/Adafruit_BluefruitLE_nRF51] (https://github.com/adafruit/Adafruit_BluefruitLE_nRF51)

Fork of the source for easy change merging is here: 
[https://github.com/rickkas7/Adafruit_BluefruitLE_nRF51] (https://github.com/rickkas7/Adafruit_BluefruitLE_nRF51)



