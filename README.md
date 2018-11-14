# TapClock
A WatchX Clock based on 
* WatchX libs provided by ArgeX
  * Especially the MPU6050 lib and Demo Code from Korneliusz Jarzebski
* BasicWatch v1 from kghunt
* OLED Library SSD1306Ascii by Greiman  
* Using Arduino 1.8.5 IDE

The Display is shown after tapping or shaking the clock.<br>
You can adjust the sensity by modify **mpu.setMotionDetectionThreshold** and/or **mpu.setMotionDetectionDuration** values<br>
<br>
The Display shows Date & Time, Uptime (right-top) and Battery level.  
  
v0.4.1
* Power saving using idle mode and disabling/enabling ADC  
  
v0.5.1
* Changed MPU6050 library to I2CDEVLIB https://github.com/jrowberg/i2cdevlib 
  * You need **I2Cdev** and **MPU6050** from https://github.com/jrowberg/i2cdevlib/tree/master/Arduino 
  * You need to remove the original MPU library
* Power saving using now 32u4's "SLEEP_MODE_PWR_DOWN". From my knowledge the highest power saving mode.
  * Modified interrupt handling needed for 32u4 and MPU6050 (latched interrupt)  
* Around 20-21hrs runtime
  * As of power saving "Uptime" shows now the **real 32u4 runtime** instead of timed uptime.  
  * After 20hrs running my "Uptime" shows a value of 3 minutes :-)  
  
v0.5.2
* Added USB Power detection  
* Charging is shown as a glowing right LED if the watch is "shaked or tapped on"  
* The Clock stays active if Usb Power if connected and don't go to sleep
* As long as the RTC has power the Clock is no longer set back to compile time on a device reset or upload  
  
v0.5.5
* Sketch needs MPU calibated values which you can create with the WatchX_IMU_Zero_0x69.ino from i2cdevlib/mpu6050 library
* After wakeing up you need to move the clock to two positions defined by angle min/max values inside the sketch before the clock is shown.
* Angle values can be shown with **#define SHOW_ANGLE  false/true**
  
<br>
<br>
Work in progress...
