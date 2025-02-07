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
	  float sensorVoltage = (sensorValue * 3.3) / 4095; // calculating voltage from sensor pin value, reference voltage, and resolution of pot
	  delay(50);                              // Wait for 50 milliseconds
### 10.) I added the following code after finding sensorVoltage to monitor the voltage on the serial bus
	  Serial.println(sensorVoltage); // printing voltage to serial monitor
### 11.) I then modified the original delay to 100ms. Now the entire loop looks like this:
	  int sensorValue = analogRead(sensorPin); // storing 'sensorPin' value in sensorValue
	   float sensorVoltage = (sensorValue * 3) / 4095; // calculating voltage from sensor pin value, reference voltage, and resolution of pot
	   Serial.println(sensorVoltage); // printing voltage to serial monitor
	   delay(100);                              // Wait for 100 milliseconds
### 12.) I verified and uploaded the code to the ESP32. It compiled first try and upon checking the serial monitor, the voltage reading was indeed being varied by the pot! Although, it was rounding to the nearest integer.

## 2/1: I start take home portion

### 1.) I get the breadboard, ESP32, usb c cable, and touch sensor from my kit
### 2.) I open the lab manual and go to the linked website in part 2: https://docs.sunfounder.com/projects/umsk/en/latest/03_esp32/esp32_lesson22_touch_sensor.html

### 3.) I wire the 3v of the breadboard to the pos. rail of breadboard, gnd to the neg. rail, and analog A0 to the IO port of the touch sensor. For the touch sensor, I wire VCC to the pos. rail of the breadboard, and for GND I wire that to the neg. rail of the breadboard.
### 4.) I plug the ESP32 into my computer and launch arduino IDE.
### 5.) I copy and paste the code from website into arduino IDE.
### 6.) I modify a line of code to fit my setup:
	const int sensorPin = 25;
### to
	const int sensorPin = A0;
#### 7.) I verified and uploaded the code to the ESP32, no issues. 
### 8.) I launched serial monitor to verify that the sensor indeed works. It looks like both sides of the circuit board in the large circular area detect touch.
### 9.) Now I set out to modify the code according to the lab manual. I need to get the LED to blink when I touch the sensor. 
### 10.) I go back into my esp32-blink-project to view the code and see what line to add to declare the built-in LED. I added the following code: 
	// Define the Built-in LED 
	int ledPin = LED_BUILTIN;
### 11.) Below where we declared the sensorPin as an input, I add this line code to declare the led pin as an output:
	  pinMode(ledPin, OUTPUT);        // Set the built-in LED as output
### 12.) In the main loop, I added the following lines of code in order to turn the led on when the sensor is touched and turn the led off when there is no touch on the sensor.
	digitalWrite(ledPin, HIGH);   // turn the LED on when touch is detected
### and
	digitalWrite(ledPin, LOW);    // turn the LED off when no touch is detected
### 13.) I verified and uploaded the code to the ESP32
### 14.) I tested and confirmed that the code works as intended. Now every time I press the sensor, the LED blinks.
### 15.) I take pictures of my github, the circuit, and a working video to upload to canvas. I uploaded the arduino code under sensor_blink_code in my github repo.

### (2/6): Fix the potentiometer code, changing voltage to 3.3 volts and uploading to github
# Reflection:
## 1.) How long did it take you to complete this assignment?  
### The lab-part of the assignment took me until the lab finished, so it was a very reasonable amount of time.
### Take-home part took around the same amount of time as the lab part. I'd say it's maybe a little long, especially considering how much documentation goes into this. Although I'm sure I'll get faster at this with time. 
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