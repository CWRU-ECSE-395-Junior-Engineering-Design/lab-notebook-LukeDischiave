## Luke Dischiave
## ECSE 395 
## Lab #3: Playing with sensors
## 01/31/25

# Purpose: 
## To learn how to program ESP32 microcontroller and have it interact with various sensors and potentiometers

# Numbered list of steps I did to complete:
## 1.) I opened the lab manual and found the potentiometer in my lab kit, some wires, the ESP32 microcontroller, and breadboard. I used my usbc-to-usbc cable to connect to my computer.
## 2.) I went to the sunfounder website in the lab manual to reference the circuit I am supposed to build
## 3.) Since the ESP32 I have is not the same as the one on the website, I had to find 3V on my board and connect to the positive rail on the breadboard. I connected the board as follows:
### 1.) Analog pin A0 on the ESP32 to OUT on the pot
### 2.) GND on the ESP32 to neg. rail on breadboard
### 3.) 3V on the ESP32 to the pos. rail on breadboard
### 4.) GND on the pot to neg. rail, and VCC on pot to pos. rail on breadboard

## 4.) I plugged in my ESP32 to my computer using the usbc cable and opened ArduinoIDE.
### 5.) I copied the code from the sunfounder website into the Arduino IDE.
### 6.) I modified the following line of code to adapt to my design:
	const int sensorPin = 25;	
### to
	const int sensorPin = A0;
### 7.) After verifying the code and pushing it to the ESP32, I went to the serial monitor and verified that my potentiometer was indeed changing the value being read at that pin.
### 8.) Following the Lab manual now, I changed the loop so now inside the loop reads as follows:
	int sensorValue = analogRead(sensorPin); // storing 'sensorPin' value in sensorValue 
	delay(50);                              // Wait for 50 milliseconds
### 9.) I created a new float called sensorVoltage to store the voltage that is being read at the data line A0. I used the formula: Voltage = AnalogValue × ReferenceVoltage / Resolution. For AnalogValue I used the sensorValue, for ReferenceVoltage, I used 3v, and for Resolution I used 4095, which is the max value of the pot.
	  int sensorValue = analogRead(sensorPin); // storing 'sensorPin' value in sensorValue 
	  float sensorVoltage = (sensorValue * 3) / 4095; // calculating voltage from sensor pin value, reference voltage, and resolution of pot
	  delay(50);                              // Wait for 50 milliseconds
### 10.) I added the following code after finding sensorVoltage to monitor the voltage on the serial bus
	  Serial.println(sensorVoltage); // printing voltage to serial monitor
### 11.) I then modified the original delay to 100ms. Now the entire loop looks like this:
	  int sensorValue = analogRead(sensorPin); // storing 'sensorPin' value in sensorValue
	   float sensorVoltage = (sensorValue * 3) / 4095; // calculating voltage from sensor pin value, reference voltage, and resolution of pot
	   Serial.println(sensorVoltage); // printing voltage to serial monitor
	   delay(100);                              // Wait for 100 milliseconds
### 12.) I verified and uploaded the code to the ESP32. It compiled first try and upon checking the serial monitor, the voltage reading was indeed being varied by the pot! Although, it was rounding to the nearest integer.
# Reflection:
## 1.) How long did it take you to complete this assignment?  
### The lab-part of the assignment took me until the lab finished, so it was a very reasonable amount of time.
### I have not started the take-home part just yet.
## 2.) What level of difficulty would you associate with this assignment?  
### Low
## 3.) If you associated medium/high difficulty with this assignment, what aspect did you find the most difficult?  
## 4. How comfortable do you currently feel with the course content?  
### Very comfortable
## 5. Do you have any additional information or feedback you would like to share with the instructors?
### Not at the moment

# In-class 1/29; Out of class 2/1
## My team and I created virtual sticky notes to represent facts on the problem situation that we are designing for, based off the interview with the stakeholder (affinity clustering). We created several categories: inferences, implementation, problems, people, and cats. After class, we committed to create one persona per person for a total of three. Attached is the persona I created and the affinity clustering.
![[Pasted image 20250201230826.png]]
![[Pasted image 20250201230215.png]]
## Reflection
## 1. How long did it take you to complete this assignment?  
### About 1-2 hours
## 2. What level of difficulty would you associate with this assignment?  
### Easy
## 3. If you associated medium/high difficulty with this assignment, what aspect did you find the most difficult?  
## 4. How comfortable do you currently feel with the course content?
### Comfortable
## 5. Do you have any additional information or feedback you would like to share with the instructors? 
### Not at the moment