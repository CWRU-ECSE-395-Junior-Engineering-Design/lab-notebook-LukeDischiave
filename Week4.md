## Luke Dischiave
## ECSE 395 
## 02/7/25

# Weekly activities:
## I fixed our project plan and project concept to fit closer to the instructor's guidelines. We completed affinity clustering using figma, and submitted a video of our video going over our stakeholder's problem and our personas.

# Lab #4:
## Purpose: To learn how to program ESP32 microcontroller and have it interact with motors
## Steps: 
### 1.) Accepted actuator adventures assignment and clones the repo to my device using github desktop
### 2.) Added the cloned repo as a vault in obsidian so I can create the readme.md

### 3.) Opened the existing readme and deleted its contents, added generic template

### 4.) Grabbed ESP32, TT motor (DC Gear Motor), Motor Driver Module, breadboard, screwdriver, and jumper cables to construct circuit

### 5.) Connected motor to motor b on motor driver. powered + rail with ESP32 3.3V and grounded - rail with gnd from ESP32, connected vcc on the motor driver to +, and gnd to -. Lastly, I plugged in B-1A and B-2A on the motor driver to 12 and 27 respectively (since this is a DC motor.
### 6.) Copied code from website to arduino IDE

### 7.) Modified the following code:
	const int motorB_1A = 26;
	const int motorB_2A = 25;
### to
	const int motorB_1A = A0;
	const int motorB_2A = A1;
### 8.) Uploaded to the ESP32 and observed behavior (in README)

### 9.) Changed analogWrite() from 255->200 and noted observed behavior
### 10.) swapped analogWrite() values (from motorB_1A -> motorB_2A) and noted observed behavior
### 11.) I modified the delay from 5000 to 2500, and noted changes in behavior.
### 12.) Now I want the motor to run forward for 5s, stop for 2s, run backward for 5s and then stop for 2s. Forward = spin right, backward = spin left. 
### 13.) updated the code to the following and uploaded to motor:
	  pinMode(motorB_1A, OUTPUT);  // set motor pin 1 as output
	  pinMode(motorB_2A, OUTPUT);  // set motor pin 2 as output
	  analogWrite(motorB_1A, 0);  // set motor speed (0-255)
	  analogWrite(motorB_2A, 255);
	  delay(5000);
	  analogWrite(motorB_1A, 0); 
	  analogWrite(motorB_2A, 0);
	  delay(2000);
	  analogWrite(motorB_1A, 255);  // set motor speed (0-255)
	  analogWrite(motorB_2A, 0);
	  delay(5000);
	  analogWrite(motorB_1A, 0);  
	  analogWrite(motorB_2A, 0);
	  delay(2000);
## Take home portion of lab 2/9
### 1.) I went to the website and copied the code: https://docs.sunfounder.com/projects/umsk/en/latest/03_esp32/esp32_lesson33_servo.html

### 2.) placed ESP32 in breadboard, and powered the + rail and grounded - rails. I gave power and gnd to servo motor. I connected the servo motor to A0 on ESP32
### 3.) changed 
	const int servoPin = 25;
### to
	const int servoPin = A0;
### 4.) went to tools -> manage libraries and added ESP32servo 
### 5.) uploaded code to the board and noted observations in readme 
### 6.) I changed numerous parameters and noted the changes in the motor

### 7.) Changed delay of first rotation to 10, and changed angle of second rotation to 90deg, with delay of 5 so it would be faster.

## Reflection: 
### 1. How long did it take you to complete this assignment?  
### 2. What level of difficulty would you associate with this assignment?  
### 3. If you associated medium/high difficulty with this assignment, what aspect did you find the most difficult?  
### 4. How comfortable do you currently feel with the course content?  
### 5. Do you have any additional information or feedback you would like to share with the instructors?