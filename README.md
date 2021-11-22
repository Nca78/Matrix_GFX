# Matrix_GFX
Arduino library for LED matrix displays, compatible with Adafruit_GFX but lighter to save as much memory as possible on Atmega328 boards

## Arduino boards Compatibility
This library have been tested on atmega328 (Uno, Nano), ESP8266 and ESP32, it should be compatible with most other boards but I have not tested them.

## Matrix compatibilities
At the moment the library supports:
 - MAX7219 (and MAX7221)
 - TM1640
 - HT16K33
 - simulated matrices on OLED (I2C only, SSD1306 & SH1106)
 *OLED has only been tested on 128*64 screens at the moment, other resolutions might or might not work, please report if you test*

## Rotation
Rotation can be managed 8x8 matrix by 8x8 matrix or for all matrices at the same time.
To apply to all matrices, pass no matrix index and the constant GFXMATRIX_ALL will be used by default.
For example:
```myMatrix.setRotation(2)```

## Documentation
### Text scrolling
The scrolling function is non-blocking, it works in 2 steps :
1. Declare strings you want to scroll in PROGMEM to save RAM ``const static char scrollString[] PROGMEM = "I CAN SCROLL TEXT!";``
2. Initialize the scrolling ``matrix.scrollInit(scrollString, 0, 15, 200);`` here scrolling area starts at pixel 0, it is 15 pixels wide and we wait 200ms between each scroll step.
3. Call the refresh function as often as possible to update the scrolling text ``matrix.scrollRefresh(true);``. Pass false instead of true if you don't want the library to refresh the matrix immediately, for example if you want to make another update on the display. In that case the scrolling text won't be refreshed until you call the ``matrix.display()`` function

### Everything else
Please see the examples, they show initialization of all matrices types and use all the functions implemented in the library.
Basically, the syntax for the drawing methods is the same than in Adafruit_GFX.



