# Matrix_GFX
Arduino library for LED matrix displays, compatible with Adafruit_GFX but lighter to save as much memory as possible on Atmega328 boards

## Arduino boards Compatibility
This library have been tested on atmega328 (Uno, Nano), ESP8266 and ESP32, it should be compatible with most other boards but I have not tested them.

## Matrix compatibilities
At the moment the library supports MAX7219 (and MAX7221) and TM1640
See the examples for both, they show all the functions of the libraries.

## Rotation
Rotation can be managed matrix by 8x8 matrix or for all matrices at the same time.
To apply to all matrices, pass no matrix index and the constant GFXMATRIX_ALL will be used by default:
setRotation(2)


