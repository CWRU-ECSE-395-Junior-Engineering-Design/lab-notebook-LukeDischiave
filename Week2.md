## Luke Dischiave
## ECSE 395 
## Lab #1 & 2: ESP32
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
## 1.) How long did it take you to complete this assignment?
## 2.) What level of difficulty would you associate with this assignment?
### Low
## 3.) If you associated medium/high difficulty with this assignment, what aspect did you find the most difficult?
### N/A

## 4.) How comfortable do you currently feel with the course content?
### I'm reasonably comfortable now with the content

## 5.) Do you have any additional information or feedback you would like to share with the instructors?
### Personally, I feel like the assignments are a little too verbose and this might be causing a little confusing for me. If they were worded a bit more concisely, it might be easier for me to understand.