# Odometer mod tool for Nissan leaf with 24C16 eeprom
Arduino based, read/write 24C16, dump as HEX and printable ASCII, and C-code array ready

Based on this project https://github.com/xiaolaba/24C16_reader

## Disclaimer
This has been written as a tool to correct Nissan leaf odometer displays. Please use this legally and 
don't get up to any funny business. I do not take any responsibility for anyone using this tool in
any manner that is not legitimate and legal.

```
/*
 * Dump 24C16 to screen, Write encoded odometer value to eeprom.
 * 
 * Arduino IDE 1.8.9 (Windows Store 1.8.21.0)
 * 
 * hardware connection,
 * 
 * 24C04 pin#   <-> Ardunino Nano pin# (Atmega168)
 * 1, A0        <-> GND
 * 2, A1        <-> GND
 * 3, A2        <-> GND
 * 4, GND       <-> GND
 * 5, SDA       <-> A4, SDA(Mega168/328)
 * 6, SCL       <-> A5, SCL(Mega168/328)
 * 7, /WP       <-> GND, always enable write
 * 8, VCC, +5V  <-> VCC, +5V
 * 
 * Serial, 115200 baud
 */
```

## wiring, testing  
![odomod_24C16_reader.JPG](odomod_24C16_reader.JPG)  

  purple-blue
  brown-orange
  white-green
  grey-white
  black-green
  
## Result,  

![odomod_24C16_reader_ATmega168_16MHz.JPG](odomod_24C16_reader_ATmega168_16MHz.JPG)  

## How to use
Remove your cluster from the leaf, remove the back cover. Solder some wires onto the eeprom pins.
Connect the eeprom pins to your arduino as shown.
connect Arduino Nano to PC, open terminal program, 115200baud, send command 'r' to dump eeprom
Send command 'w 135001' to write odometer value 135001 to eeprom. 

## library used, modified, 
https://github.com/yazug/EEPROM24C04_16, no fork, but local copy
https://github.com/xiaolaba/24C16_reader, Majority based on this project


## Source code  
![leaf_odo_mod.ino](leaf_odo_mod.ino)  


## modified library
![Eeprom24C04_16.cpp](Eeprom24C04_16.cpp)  
![Eeprom24C04_16.h](Eeprom24C04_16.h)
