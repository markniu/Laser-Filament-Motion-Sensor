# laser-filament-motion-sensor
Independent laser motion sensor to sense filament clog or runout.

### What is it ?
Block Diagram


### Why I make it?

### What makes it specials?


### How to install?

 Name     |      Description   
 -------- | :-----------:   
 MOTOR_IN     | unplug the extruder motor line and then connect to this port  
 MOTOR_OUT     | connect this port to your extruder motor with the line in the parcel.
 5V     | power input 5V.
 GND    | power input GND from your printer  
 S      | output of filament clogged or runout,active low.connect this line to stop or runout pin on your printer control board that can pause the printing process.
Buzzer  | if detect the filament clogged or runout it will sound, >85db.
 LED0     |  .
 LED1     | Motion detection output,if there is movement on top of the laser sensor,it will light on.
 RESET button     | clear the buzzer sound,it will also reset the MCU chip
 USB     | 1,set the sensitive value.2,get the motion data of filament and extruder motor.3,flash firmware if there is new firmware.serial port at baud rate 9600.
 Optical_Laser_Chip     | tracking the filament motion. the recommended distance between the chip and filament is at 3~4mm.Compliance to IEC/EN 60825-1 Eye Safety, Class 1 LASER power output level
 


### How to check


