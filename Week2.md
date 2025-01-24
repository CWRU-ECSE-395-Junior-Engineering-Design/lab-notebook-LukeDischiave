## Luke Dischiave
## ECSE 395 
## Lab #1: ESP32
## 01/17/25, 1/24/25

# Purpose: 
## To learn how to progam ESP32 microcontroller 

# Numbered list of steps I did to complete:
## 1.) Installed latest Arduino IDE and drivers according to the tutorial on canvas
## 2.) added README.md (this file)
## 3.) Copied the code from https://learn.adafruit.com/adafruit-esp32-feather-v2/blink into Arduino IDE
## 4.) Code did not compile/verify so I changed the first line of code: 
	int led = LED_BUILTIN;
## to 
	int led = 13;
## since blinking LED is on PIN 13 on the board. This compiles.
## 5.) I realized I had the wrong board selected, so I selected the Adafruit feather ESP V2 and then reverted 
	int led = 13;
## to
	int led = LED_BUILTIN;
## The original code now compiles
## 6.) I push the code to the ESP and voila, it work!

# Reflection:
## Joe got farther than us in the lab so he copied the code to the ESP32 first. Rob and I were figuring out how to complete the rest of the lab. There was an error with Joe's computer and the ESP32 microcontroller. This was on 1/17.

## On 1/24, I proceeded to finish the blinking ESP. 
