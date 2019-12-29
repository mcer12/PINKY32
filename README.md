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

## Notes
- PINKY32 has built-in pink or white LED, it's connected to PA4. You can test it with Blink sketch.
