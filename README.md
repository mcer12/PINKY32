# PINKY32
PINKY32 is a compact low-power STM32F030F4P6 dev board.
- Tiny. Smaller form factor than Arduino Nano (see images)
- CH340 onboard for easy firmware flashing and serial communication. Perfect for fast development.
- Simple slider switch to select boot mode
- Low quiescent current voltage regulator => it's low-power application ready drawing only few uA in shutdown sleep mode.
- Compatible with Arduino IDE (stm32duino core)

STM32F030 is capable of 16bit PWM (have tested 12bit in Arduino IDE), this is perfect for slow dimming for example. Much better than 8bit Atmega328 in arduino.

![alt text](https://github.com/mcer12/PINKY32/raw/master/Images/pinout.png)

## Flashing in Arduino IDE
1. In arduino IDE head over to Boards manager and download stm32duino arduino core. If you already have it installed, it's recommended to update to latest version.
2. Select STM32F030 board according to the screen below.  
![alt text](https://github.com/mcer12/PINKY32/raw/master/Images/arduino_settings.png)
3. Set the onboard slider switch to position 1
4. Connect PINKY32 to the computer, new available COM port should pop up.
5. Select the appropriate COM port and hit upload.
6. After that's done, set the switch to position 0 and reset the board (pushing the onboard button or power cycle).


## Notes
- PINKY32 has built-in pink or white LED, it's connected to PA4. You can test it with Blink sketch.
- By default, pins PA3 (RX) and PA2 (TX) are used for Serial output in Arduino IDE. If you want to debug via USB, use this:  
  > Serial.setRx(PA10);  
  > Serial.setTx(PA9);  
  
  before Serial.begin();  
  keep in mind, that moving Serial to PA9 and PA10 will prevent you from using I2C.
- If you're running out of Flash storage, you can disable Serial in compilation settings in Arduino IDE, to save some space.
