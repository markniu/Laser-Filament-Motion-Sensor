# laser-filament-motion-sensor
This is a independent laser motion sensor to sense filament clog or runout.
![board diagram](https://gitee.com/markyue/pandapi_wiki/raw/master/imges/filament/531083500.jpg)  
[Test video](https://youtu.be/U-0V2owizyw)
### What is it ?
Block Diagram
![board diagram](https://gitee.com/markyue/pandapi_wiki/raw/master/imges/V28/26171942.png)  
if it detect the clog or runout,it will set the output signal line to low or high voltage which tell the mother board to pause printing.
it works with the motherboard which have run out connector. 

### Why I make it?

### What makes it specials?
1. There is a Micro processor on the board that read the sensor and process the algorithm instead of directly by motherboard,it will more stable.
2. This tracking system also does not require code wheel, code strip and any special marking on tracking surface for motion control or tracking purposes
3. You can change the sensitivlty,output alarm time and output signal level by [serial tools](https://github.com/markniu/Laser-Filament-Motion-Sensor/blob/main/tools/Fsensor_tool.exe) or send command.
### How to install?

[Install on Ender3/5 CR10](https://github.com/markniu/Laser-Filament-Motion-Sensor/wiki/Install-on-Ender3-5,CR10)

![board diagram](https://gitee.com/markyue/pandapi_wiki/raw/master/imges/filament/1151922.jpg) 

 Name     |      Description   
 -------- | :-----------   
 5V     | power input 5V.
 GND    | power input GND from your printer  
 S      | output of filament clogged or runout,active low.connect this line to the runout pin on your printer control board that can pause the printing process.
 MOTOR_IN     | unplug the extruder motor line and then connect to this port  
 MOTOR_OUT     | connect this port to your extruder motor with the line in the parcel.
 Buzzer  |  will sound when the clog or runout is detected, >85db.
 LED0     |  will light on when the clog or runout is detected.
 LED1     | Motion detection output,if there is movement on top of the laser sensor chip,it will light on.
 RESET button     | clear the buzzer sound,it will also reset the MCU chip
 USB     | 1,set the sensitive value.2,get the motion data of filament and extruder motor.3,flash firmware if there is new firmware.serial port at baud rate 115200.
 Optical_Laser_Chip     | tracking the filament motion. the recommended distance between the chip and filament is at 3~4mm.Compliance to IEC/EN 60825-1 Eye Safety, Class 1 LASER power output level
 
### Supported drivers 
have test the A4988/TMC2208/TMC2209
 Driver     |      mode  | current    
 -------- | :-----------   | :-----------  
 A4988     |  . | >500mA
 TMC2208    |  standalone | >500mA
 TMC2209     |  standalone | >500mA
 
 
note: If the motor current is too low, it can not work probably,movement cannot be recognized,because this module read the wave of motor current.
recommend use it as standalone mode.for some uart mode, you need to increase the current.also there is a hardware solution for the low current,need to change 4 resistors values,you can contact me with email or facebook.

### How to check
you may need to check if it works as you expected after finishing installation at first time.   

pull the filament out of the extruder motor,and then move the extruder motor from the control panel,you can let the filament in or out of the sensor, 
just make sure there is no movement of the filament while the motor is moving.

if the motor move for  xx seconds,the buzzer will sound and the LED beside the buzzer will light on.
that means it works,and then you can clear the buzzer by press the reset botton. 

