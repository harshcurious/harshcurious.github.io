---
title: "My Experiments with Raspberry Pi: Part 1"
date: 2021-03-20T13:39:03+05:30
draft: false

# weight: 1
# aliases: ["/first"]
tags: ["Raspberry", "pi", "linux"]
author: "Harsh Kumar"
# author: ["Me", "You"] # multiple authors
showToc: true
TocOpen: false
hidemeta: false
comments: true
description: "Some rather simple projects"

disableShare: false
# to disable highlightjs
disableHLJS: false
searchHidden: true
cover:
    image: "<image path/url>" # image path/url
    alt: "<alt text>" # alt text
    caption: "<text>" # display caption under cover
    relative: false # when using page bundles set this to true
    hidden: true # only hide on current single page

---

Today I am going to run a 7 segment display off of  raspberry pi 4.

## The code I ran
```python
#!/usr/bin/env python
import RPi.GPIO as GPIO
import time

pins = [11,12,13,15,16,18,22,7]
dats = [0x3f,0x06,0x5b,0x4f,0x66,0x6d,0x7d,0x07,0x7f,0x6f,0x77,0x7c,0x39,0x5e,0x79,0x71,0x80]

def setup():
	GPIO.setmode(GPIO.BOARD)
	for pin in pins:
		GPIO.setup(pin, GPIO.OUT)   # Set pin mode as output
		GPIO.output(pin, GPIO.LOW)

def writeOneByte(val):
	GPIO.output(11, val & (0x01 << 0))
	GPIO.output(12, val & (0x01 << 1))
	GPIO.output(13, val & (0x01 << 2))
	GPIO.output(15, val & (0x01 << 3))
	GPIO.output(16, val & (0x01 << 4))
	GPIO.output(18, val & (0x01 << 5))
	GPIO.output(22, val & (0x01 << 6))
	GPIO.output(7,  val & (0x01 << 7))

def loop():
	while True:
		for dat in dats:
			writeOneByte(dat)
			time.sleep(0.5)

def destroy():
	for pin in pins:
		GPIO.output(pin, GPIO.LOW)
	GPIO.cleanup()             # Release resource

if __name__ == '__main__':     # Program start from here
	setup()
	try:
		loop()
	except KeyboardInterrupt:  # When 'Ctrl+C' is pressed, the child program destroy() will be executed.
		destroy()

```

Here is the thing, I just copied this code which was given to me. I don't know what this means. Specifically, the `dats` stuff. So let me just run and see if this works. Here is the circuit I made.

![Circuit Fritzing](/static/RaspberryPi/20thMarch21/7segmentPi.png#center)
![For the snobs](/static/RaspberryPi/20thMarch21/7segmentPi_schem.png#center)

**Remark**: the 220 $ \Omega $ resistor is  connected to power in case that is not clear.

It works :sweat_smile: . Let's carry on and celebrate with a few :camera: .

![The connection mess 1](/static/RaspberryPi/20thMarch21/photo1.jpg#center)
![The connection mess 2](/static/RaspberryPi/20thMarch21/photo3.jpg#center)

![The obligatory gif](/static/RaspberryPi/20thMarch21/7segment.gif#center)

Now that I have calmed down a little bit, let me look at the mysterious bit of code. From what's happening I know that the code switches the leds in the 7-segment display so that we loop through 0 to 9 and A to F and then 0 again. The display changes every 0.5 seconds.

Time for google :mag: . [Found it :raised_hands:](https://stackoverflow.com/questions/38997913/python-bitwise-logic-to-operate-leds). Let me rewrite the explanation in my own way.

## What Was that Code

The parts that I didn't understand were `0x3f`-like objects and the operation `<<`. 
