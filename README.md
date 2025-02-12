# TinyCircuits TinyScreen/TinyScreen+ Arduino Library

This library allows for easy use of the TinyScreen display and input buttons. 

This Arduino library is intended for use with TinyCircuits' **[TinyScreen Arduino Shield](https://tinycircuits.com/collections/leds-displays/products/tinyscreen?variant=13748964423)** and **[TinyScreen+ Arduino processor](https://tinycircuits.com/collections/processors/products/tinyscreenplus)** to easily interface with the display and buttons. Text, shapes, pixel manipulation, flipping, mirroring, and more allow you to display data, pictures, video, games or whatever you can fit in 96 by 64 pixels with 16 bit color.

*Support this library by buying products from **[TinyCircuits](https://tinycircuits.com/)***

## Basic Example

An example demonstrating and explaining most of the library functions is included. A list of further notes:

* Include the TinyScreen, SPI, and Wire libraries (Wire can be omitted from TinyScreen+ code if necessary)
* Declare TinyScreen as display, and use the correct board type(TinyScreenDefault, TinyScreenAlternate, TinyScreenPlus): TinyScreen display = TinyScreen(TinyScreenPlus);
* TinyScreen library defaults to BGR colors, and this is what the TS_8b and TS_16b color definitions use. This can be changed with setColorMode(TSColorModeRGB);
* Testing for a button press can now be done in a readable way, and works the same when the display is flipped: if (display.getButtons(TSButtonUpperLeft)) { };
* TinyScreen+ supports DMA data transfers- check the end of TinyScreen.cpp

### Initialization & Control

* **void startData(void)**
* **void startCommand(void)**
* **void endTransfer(void)**
* **void begin(void)**
* **void on(void)**
* **void off(void)**
* **void setFlip(uint8_t)**
* **void setMirror(uint8_t)**
* **void setBitDepth(uint8_t)**
* **void setBrightness(uint8_t)**
* **void setColorMode(uint8_t)**
* **void writeRemap(void)**

### Basic Graphic Commands

* **void writePixel(uint16_t)**
* **void writeBuffer(const uint8_t \*, int)**
* **void setX(uint8_t, uint8_t)**
* **void setY(uint8_t, uint8_t)**
* **void goTo(uint8_t x, uint8_t y)**

### Built-In Drawing Commands

* **void drawPixel(uint8_t, uint8_t, uint16_t)**
* **void drawLine(int16_t, int16_t, int16_t, int16_t, uint8_t, uint8_t, uint8_t)**
* **void drawLine(int16_t, int16_t, int16_t, int16_t, uint16_t)**
* **void drawRect(int16_t, int16_t, uint8_t, uint8_t, uint8_t, uint8_t, uint8_t, uint8_t)**
* **void drawRect(int16_t, int16_t, uint8_t, uint8_t, uint8_t, uint16_t)**
* **void drawHLine(int16_t, int16_t, int16_t, uint8_t, uint8_t, uint8_t)**
* **void drawHLine(int16_t, int16_t, int16_t, uint16_t)**
* **void drawVLine(int16_t, int16_t, int16_t, uint8_t, uint8_t, uint8_t)**
* **void drawVLine(int16_t, int16_t, int16_t, uint16_t)**
* **void drawTri(int16_t, int16_t, int16_t, int16_t, int16_t, int16_t, uint8_t, uint8_t, uint8_t, uint8_t)**
* **void drawTri(int16_t, int16_t, int16_t, int16_t, int16_t, int16_t, uint8_t, uint16_t)**
* **void clearWindow(uint8_t, uint8_t, uint8_t, uint8_t)**
* **void clearScreen(void)**

### I2C / GPIO

* **uint8_t getButtons(uint8_t)**
* **uint8_t getButtons(void)**
* **void writeGPIO(uint8_t, uint8_t)**

### Font

* **void setFont(void)**
* **uint8_t getFontHeight(void)**
* **uint8_t getFontHeight(const FONT_INFO&)**
* **uint8_t getPrintWidth(char \*)**
* **void setCursor(uint8_t, uint8_t)**
* **void fontColor(uint16_t, uint16_t)**
* **virtual size_t write(uint8_t)**

### DMA for SAMD

* **void initDMA(void)**
* **uint8_t getReadyStatusDMA(void)**
* **void writeBufferDMA(uint8_t \*,int)**
  

