# EngineeringNotebook_Eng3


## Table of Contents
* [Table of Contents](#Table-of-Contents)
* [skateboard deck](##skateboarddeck)
* [Exemplars](#Exemplars)
* [UsefulGitStuff](#UsefulGitStuff)
* [UsefulCircuitPythonStuff](#UsefulCircuitPythonStuff)



## Skateboard deck

### Description 

!This is the deck I desinged following the instructions that were given this helped me use some of the cad skills i learned last year and refresh my memory.

### Evidence

### <img src="https://github.com/mtimmin65/engineering-notebook/blob/main/Capture.PNG" width="500">

### Reflection 

## Trucks

### Description

!theses are the skateboard trucks i designed using fillets that i hadnt used in a while.

### Evidence

### <img src="https://github.com/mtimmin65/engineering-notebook/blob/main/Capture1.PNG" width="500">

### Reflection


## Wheels and Bearings

### Description

!these are my wheels and bearings i had to use a revolve extrude which i hadnt done before.

### Evidence

### <img src="https://github.com/mtimmin65/engineering-notebook/blob/main/Capture4.PNG" width="500">



## Complete skateboard

### Description 

!this is my complete skateboard i used the assembly page and i put mates in to make it look like it would if it gets made.

### Evidence

### <img src="https://github.com/mtimmin65/engineering-notebook/blob/main/Capture5.PNG" width="500">



## Hello_CircuitPython

### Description & Code

This assingment was making an led turn red and blue using the led on the adifruit metro.

```
dot = neopixel.NeoPixel(board.NEOPIXEL, 1)

print("Make it red!")
dot.brightness=0.2
while True:
dot.fill((255,0,0))
time.sleep(.5)
print("Make it red!")
dot.brightness=0.2
dot.fill((0,0,255))
time.sleep(.5)
```

### Evidence

<img src="https://github.com/mtimmin65/engineering-notebook/blob/main/IMG-202814240%20(1).gif" width="500">

### Reflection
!i didnt have any issues accept trying to figure out how to change the color.


## CircuitPython_Servo

### Description & Code

```python
"""CircuitPython Essentials Servo standard servo example"""
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
!this assingment was pretty simple i didnt have any isues with wiring or the code.



## CircuitPython_ultrasonic sensor

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
        r = max(min(15*(20-dist),255),0)
        g = max(min(15*(dist-20),255),0)
        b = max(min(-abs(15*(20-dist))+225,255),0)
        dot.fill((int(r), int(g), int(b)))
    except RuntimeError:
        print("Retrying!")
    time.sleep(0.1)
```

### Evidence
     
<img src="https://github.com/ezell38/Hello_CircuitPython/blob/main/Images/IMG-86812912-3 (1).gif?raw=true" alt="CircuitPython_LCD" width="500">
     
### Wiring

<img src="https://github.com/ezell38/Hello_CircuitPython/blob/main/Images/Capture.1.PNG?raw=true" alt="CircuitPythonDistance" width="500">

### Reflection

This assignment was hard because I kept saving the code to a file on my computer and not my Metro board. I also used some code from another student and didn't adjust my wiring to fit their code which messed up my Ultrasonic sensor. 

