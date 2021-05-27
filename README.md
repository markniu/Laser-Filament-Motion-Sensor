# laser-filament-motion-sensor
This is a independent laser motion sensor to sense filament clog or runout.

### What is it ?
Block Diagram
![board diagram](https://gitee.com/markyue/pandapi_wiki/raw/master/imges/V28/26171942.png)  

### Why I make it?

### What makes it specials?


### How to install?

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
 USB     | 1,set the sensitive value.2,get the motion data of filament and extruder motor.3,flash firmware if there is new firmware.serial port at baud rate 9600.
 Optical_Laser_Chip     | tracking the filament motion. the recommended distance between the chip and filament is at 3~4mm.Compliance to IEC/EN 60825-1 Eye Safety, Class 1 LASER power output level
 


### How to check
you may need to check if it works as you expected after finishing installation at first time.   

pull the filament out of the extruder motor,and then move the extruder motor from the control panel,you can let the filament in or out of the sensor, 
just make sure there is no movement of the filament while the motor is moving.

if the motor move for  xx seconds,the buzzer will sound and the LED beside the buzzer will light on.
that means it works,and then you can clear the buzzer by press the reset botton. 

