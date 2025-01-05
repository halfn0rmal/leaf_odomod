# Odometer mod tool for Nissan leaf with 24C16 eeprom
Arduino based, read/write 24C16, dump as HEX and printable ASCII, and C-code array ready  

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
  
  
## Result,  

![odomod_24C16_reader_ATmega168_16MHz.JPG](odomod_24C16_reader_ATmega168_16MHz.JPG)  

## How to uses  
connect Arduino Nano to PC, open terminal program, 115200baud, send command 'r' to dump eeprom
Send command 'w 135001' to write odometer value 135001 to eeprom. 

## library used, modified, 
https://github.com/yazug/EEPROM24C04_16, no fork, but local copy
https://github.com/yazug/EEPROM24C04_16, no fork, but local copy


## Source code  
![leaf_odo_mod.ino](leaf_odo_mod.ino)  


## modified library
![Eeprom24C04_16.cpp](Eeprom24C04_16.cpp)  
![Eeprom24C04_16.h](Eeprom24C04_16.h)
