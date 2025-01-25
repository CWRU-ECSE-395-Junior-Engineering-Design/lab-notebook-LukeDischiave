## Luke Dischiave
## ECSE 395 
## Lab #1: ESP32
## 01/17/25, 1/24/25

# Purpose: 
## To learn how to progam ESP32 microcontroller using Arduino IDE and also modify existing code so that it behaves differently

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
## 6.) I push the code to the ESP and voila, it works!
## 7.) I take video of ESP32 blinking

## 8.) Now I start lab #2
## 9.) I changed the serial print message to: 
	  Serial.println("안녕하세요!");
	
## 10.) I changed the frequency of the blinks so that it blinks twice as fast
## 11.) I took video and uploaded new code to github

# Reflection:


