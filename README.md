# Detect clog automatically
Detect clog automatically, This is an independent laser motion sensor to sense filament clog and runout.
![board diagram](https://gitee.com/markyue/pandapi_wiki/raw/master/imges/filament/531083500.jpg)  
[Test video](https://youtu.be/U-0V2owizyw)
### What is it ?
Block Diagram
![board diagram](https://gitee.com/markyue/pandapi_wiki/raw/master/imges/filament/26171942.png)  
if it detect the clog or runout,it will set the output signal line to low or high voltage which tell the mother board to pause printing.
so it works with all the motherboard which have run out connector. 

### What makes it specials?
1. It compares the movement of extruder and filament at the same time.that means you do not need to worry about how long of the travel length and how much of the travel time in non print moves while printing with other filament sensor like [bigtree](https://www.bigtree-tech.com/products/bigtreetech-smart-filament-sensor.html)
2. There is a micro controller on the board that read the filament sensor and motor current, then process the algorithm instead of motherboard(marlin) to process which has the lowest priority and not fast enough sometimes that will make mistake.
3. For it no needs to send digital signal (0-1-0…) during movement all the time with the long signal line beside the lines of E motor which will make strong signal noise to the sensor line.
4. This tracking system also does not require code wheel, code strip and any special marking on tracking surface.
5. You can change the sensitivlty,output alarm time and output signal level by [serial tools](https://github.com/markniu/Laser-Filament-Motion-Sensor/blob/main/tools/Fsensor_tool.exe) or send command.
6. Even if there is no run out pin on the motherboard, it can also make beep alarm for your printer when it detect the filament clog or runout.
### How to install?
 The usage is almost the same as the switch filament runout sensor. there are a lot of instruction on that on the internet,[DIY filament runout sensor](https://youtu.be/gwHpXaj_6xE) , [Install runout sensor on Ender3/5 CR10](https://youtu.be/5Jt-Qc67FDo).
 
beside that I will also add more instructions  [Install on Ender3/5 CR10](https://github.com/markniu/Laser-Filament-Motion-Sensor/wiki/Install-on-Ender3-5,CR10)

![board diagram](https://gitee.com/markyue/pandapi_wiki/raw/master/imges/filament/1151922.jpg) 

 Name     |      Description   
 -------- | :-----------   
 5V     | power input 5V.
 GND    | power input GND from your printer  
 S      | output of filament clogged or runout,active low.connect this line to the runout pin on your printer control board that can pause the printing process.make sure your printer have runout function,sometime you need to configure the firmware.
 MOTOR_IN     | unplug the extruder motor line and then connect to this port  
 MOTOR_OUT     | connect this port to your extruder motor with the line in the parcel.
 Buzzer  |  will sound when the clog or runout is detected, >85db.
 LED0     |  will light on when the clog or runout is detected.
 LED1     | Motion detection output,if there is movement on top of the laser sensor chip,it will light on.
 RESET button     | clear the buzzer sound,it will also reset the MCU chip
 USB     | 1,set the sensitive value.2,get the motion data of filament and extruder motor.3,flash firmware if there is new firmware.serial port at baud rate 115200.
 Optical_Laser_Chip     | tracking the filament motion. the recommended distance between the chip and filament is at 3~4mm.Compliance to IEC/EN 60825-1 Eye Safety, Class 1 LASER power output level
 
 
here is the data output from the micrusb while printing. we can see this module can read the filament move distance and the E axis motor move distance.
 ![board di](https://gitee.com/markyue/pandapi_wiki/raw/master/imges/filament/0901180530.jpg) 
 
#### Setting 
Connect sensor to your printer with microUSB port,run [Fsensor_tool](https://github.com/markniu/Laser-Filament-Motion-Sensor/blob/main/tools/Fsensor_tool.exe), choose the serial port and click open.and then you can see the value on the board,and set them as you like.

 Name     |      Description   
 -------- | :-----------  
 Sensitivity | Time period no filament movement.the move comparison time period is 0.5s,so if you set 5, it means if only the motor moves for continue 2.5s,it will be triggered and alarm.
 Alarm and Signal output time | Time of the buzzer sound and signal output, it can be set always on or other time you want.
 Signal output Logic level | LOW or HIGH,the default is LOW.  the recommended value is LOW.

### Supported drivers 
have test the A4988/TMC2208/TMC2209

 Driver     |      mode  | current    
 -------- | :-----------   | :-----------  
 A4988     |  . | >500mA
 TMC2208    |  standalone | >500mA
 TMC2209     |  standalone | >500mA
 
#### Support Colors:
 I have tested several colors of filaments, and this sensor is very sensitive to all of these colors, including black, red, white, and transparent filaments.
 
 ### How to check
you may need to check if it works as you expected after finishing installation at first time.   

pull the filament out of the extruder motor,and then move the extruder motor from the control panel,you can let the filament in or out of the sensor, 
just make sure there is no movement of the filament while the motor is moving.

if the motor move for  xx seconds,the buzzer will sound and the LED beside the buzzer will light on.
that means it works,and then you can clear the buzzer by press the reset botton. 

### note: 
If the motor current is too low, it can not work probably,movement cannot be recognized,because this module read the wave of motor current.
recommend use it as standalone mode.for some uart mode, you need to increase the current.also there is a hardware solution for the low current,need to change 4 resistors values,you can contact me with email or facebook.

#### [STL File](https://www.thingiverse.com/thing:4887998)
mount on the PCB with 2 * Self Tapping Screw(M2.3*8)

### [Where to buy ](https://www.pandapi3d.com/product-page/laser-filament-motion-sensor)

### [Facebook Support](https://www.facebook.com/groups/380795976169477/)

