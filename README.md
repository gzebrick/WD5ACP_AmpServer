By Guy Zebrick. WD5ACP

<img width="439" height="608" alt="sc" src="https://github.com/user-attachments/assets/9b3f0692-7a68-497a-864c-d92970d4d21e" />

Program to add a webpage to the KPA500 amplifier plus local display of 4 parameters on color touchscreen
The program was written for a CYD (Cheap Yellow Display) ESP32 microcomputer and programmed in C++
using Visual Studio Code

<img width="1236" height="719" alt="AmpServeWeb" src="https://github.com/user-attachments/assets/06e62537-8e7b-4ffd-b38c-42ae1467b775" />


3D case if you want can be found here:
https://www.tinkercad.com/things/hLtHflTGTa5-newcydvertcasev1

<img width="1899" height="840" alt="AmpServser" src="https://github.com/user-attachments/assets/692f465b-61a3-4044-86ea-be60f940dd0b" />


Requies seperate TLL<>RS232 adapter board for physical DB-9 connector to amplifier's PC RS232 port
I used one of these from Amazon...
5PCS MAX3232 RS232 to TTL Converter Module 3.3V-5V for Arduino MCU
The board is plug and play to the I2C port using the small cable that comes with the CYD
I2C     <>  TTL Board
RED     <>  VCC
BLUE    <>  RXD
YELLOW  <>  TXD
BLACK   <>  GND
#define RXD2 22 // I2C SDA pin 25on CYD board is GPIO 25, which is also RXD2 for RS232 serial to RX
#define TXD2 27 // I2C SCL pin 32 on CYD board is GPIO 32, which is also TXD2 for RS232 serial to TX

Code includes WiFi management as well as display, LED, Serial port and non-volatile storage

eSPI settings needed for 2.8" 240x320:
#define ILI9341_DRIVER // Generic driver for common displays
#define TFT_WIDTH 240 // ST7789 240 x 240 and 240 x 320
#define TFT_HEIGHT 320 // ST7789 240 x 320
#define TFT_MISO 12  //19
#define TFT_MOSI 13  //23
#define TFT_SCLK 14  //18
#define TFT_CS 15  // Chip select control pin
#define TFT_DC 2   // Data Command control pin
#define TFT_RST -1 // Set TFT_RST to -1 if display RESET is connected to ESP32 board RST
#define TOUCH_CS 33 // 21 Chip select pin (T_CS) of touch screen
