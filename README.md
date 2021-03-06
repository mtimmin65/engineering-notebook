# EngineeringNotebook_Eng3


## Table of Contents
* [Table of Contents](#Table-of-Contents)
* [Skateboard deck](#skateboard-deck)
* [Trucks](#Trucks)
* [Wheels and Bearings](#Wheels-and-Bearings)
* [Complete Skateboard](#Complete-Skateboard)
* [Hello_CircuitPython](#Hello_CircuitPython)
* [CircuitPython_servo](#CircuitPython_servo)
* [CircuitPython_ultrasonic sensor](#CircuitPython_ultrasonic-sensor)

### [Onshape Link](https://cvilleschools.onshape.com/documents/baaa6163c1cb7c38eceaa847/w/88c5bf87b941faebf976384e/e/ec18fe06272169d29210d203?aa=true)

## Skateboard deck

### Description 

This assignment was to make a skateboard using differnt skills. There are many different parts to this project. This is the deck.

### Evidence

### <img src="https://github.com/mtimmin65/engineering-notebook/blob/main/Capture.PNG" width="500">

### Reflection 

This assignment was helpful because it used some mirroring and filleting techniques. When mirroring you have to find a median point using a construction line or just any middle intersecting line. I later used mirroring techniques in my robot arm project.

## Trucks

### Description

These are the trucks I have made my skateboard project. Using different onshape, logical skills and following the step by step instructions.

### Evidence

### <img src="https://github.com/mtimmin65/engineering-notebook/blob/main/Capture1.PNG" width="500">

### Reflection

This assignment was difficult because I had to figure out how to use the revolve tool. a lot of fillets and interlocking peices. It took a bit of trail and error. For using the revole tool you must make a shape that when revoled will be the shape you want so you must make sure all of your dimensions are correct.

## Wheels and Bearings

### Description

These are My wheels and bearings i had to use a revolve extrude which i hadnt done before.

### Evidence

### <img src="https://github.com/mtimmin65/engineering-notebook/blob/main/Capture4.PNG" width="500">

### Reflection

This assignment was difficult because I had to figure out how to use the revolve tool to be a certain radius. you have to define your shape and create a mid point to revole around.

## Complete Skateboard

### Description 

This is my complete skateboard which i have made puting together all of my parts.

### Evidence

### <img src="https://github.com/mtimmin65/engineering-notebook/blob/main/Capture5.PNG" width="500">

### Reflection

Overall I only had minor issues making this project. It was very fun and helpful in getting back into the swing of using cad. I enjoyed this assignment.

## Hello_CircuitPython

### Description & Code

This assingment was making an led turn red and blue using the led on the adifruit metro.

```
dot = neopixel.NeoPixel(board.NEOPIXEL, 1)

print("Make it red!")
dot.brightness=0.2
while True:
dot.fill((255,0,0)) #Changes color to red
time.sleep(.5)
print("Make it Blue!")
dot.brightness=0.2
dot.fill((0,0,255)) #Chages color to blue
time.sleep(.5)
```

### Evidence

<img src="https://github.com/mtimmin65/engineering-notebook/blob/main/IMG-202814240%20(1).gif" width="500">

### Reflection

I always have some sort of trouble with the code. With a little help from [elias zell](https://github.com/ezell38/Hello_CircuitPython) I figured it out and got it working. Using the internet and peers as reasources.

## CircuitPython_servo

### Description & Code

This assignment was to make a servo move back and forth. I had to find code and a wiring diegrahm.

```python
import time
import board
import pwmio
import servo

# create a PWMOut object on Pin A2.
pwm = pwmio.PWMOut(board.A2, duty_cycle=2 ** 15, frequency=50)

# Create a servo object, my_servo.
my_servo = servo.Servo(pwm)

while True:
    for angle in range(0, 180, 5):  # 0 - 180 degrees, 5 degrees at a time.
        my_servo.angle = angle
        time.sleep(0.05)
    for angle in range(180, 0, -5): # 180 - 0 degrees, 5 degrees at a time.
        my_servo.angle = angle
        time.sleep(0.05)

```

### Evidence

<img src="WIN-20210917-15-19-55-Pro (2).gif" alt="servodemo" width="500">

### Wiring

<img src="https://github.com/mtimmin65/engineering-notebook/blob/main/Capture8.PNG" alt="servodemo" width="500">

### Reflection

The wiring for this assignment was hard to grasp at first. I found a good [diagram](https://learn.adafruit.com/adafruit-arduino-lesson-14-servo-motors/the-breadboard-layout-for-sweep) online. Using this diagram I worked through the previous issues and got it working.  

## CircuitPython_ultrasonic sensor

### Description and Code

This assignment was to make it so the distance on the ultrasonic sensor corresponds with the color displayed on the Metro board.

```python
import adafruit_hcsr04
import time
import board
import neopixel

sonar = adafruit_hcsr04.HCSR04(trigger_pin=board.D2, echo_pin=board.D3)
dot = neopixel.NeoPixel(board.NEOPIXEL, 1)

dot.brightness = 0.1

while True:
    try:
        dist = sonar.distance
        print((dist))
        r = max(min(15*(20-dist),255),0) #Change color to red
        g = max(min(15*(dist-20),255),0) #Change color to green
        b = max(min(-abs(15*(20-dist))+225,255),0) #Change color to green
        dot.fill((int(r), int(g), int(b)))
    except RuntimeError:
        print("Retrying!")
    time.sleep(0.1)
```
This is code from [elias zell](https://github.com/ezell38/Hello_CircuitPython)
### Evidence
     
<img src="https://github.com/ezell38/Hello_CircuitPython/blob/main/Images/IMG-86812912-3 (1).gif?raw=true" alt="CircuitPython_LCD" width="500">
This image is from [elias zell](https://github.com/ezell38/Hello_CircuitPython)

### Wiring

<img src="https://github.com/ezell38/Hello_CircuitPython/blob/main/Images/Capture.1.PNG?raw=true" alt="CircuitPythonDistance" width="500">
This image is from This is code from [elias zell](https://github.com/ezell38/Hello_CircuitPython)

### Reflection

This assignment was hard because I kept saving the code to a file on my computer and not my Metro board. I also used some code from This is code from [elias zell](https://github.com/ezell38/Hello_CircuitPython) and didn't adjust my wiring to fit their code which messed up my Ultrasonic sensor. 

