## Luke Dischiave
## ECSE 395 
## 02/14/25
# Weekly activities:
## My group and I did our brainstorming for 50 thoughts for the solution to our stakeholder's problem in class monday, and we finished up async. We also met to create our presentation on our three best ideas on tuesday, which involved sensing the weight of the water in the cat bowl using various sensors, and notifying the user when the water/food needs to be refilled in different way. In class on wed, we presented these ideas to the class. On friday, we did Lab #5. We also scheduled our second stakeholder meeting for sunday morning to ask more clarification questions. 
![](Pasted%20image%2020250214200058.png)
![](Pasted%20image%2020250214200120.png)
# Lab #5:
## Purpose: To learn how to program ESP32 microcontroller and have it interact with different sensors and add-ons. This is the fifth assignment working with the ESP32 
## Steps: 
### 1.) Accepted and cloned repo
### 2.) selected button module and rgb LED actuator
### 3.) copied code from last lab into new note in arduino ide
### 4.) I connected the RGB pins -, R, G, B into GND, 13, 12, and 27 respectively. I also provided power and ground to the rails on the breadboard
### 5.) I connected the button pins 1, 2, 3 (sense, 3.3v, gnd) to Pin 33, -, and + on the breadboard respectively. I wired it so that when the button is pressed, the circuit opens, and 3.3v no longer flows to the sense pin.
### 6.) in setup, I set the RGB pins as outputs and the button sense pin as input. 
### 7.) I programmed my circuit so that the LED blinks through red, green and blue for 500ms each color, and then waits 500ms before sequencing again. When the button is pressed, it stops blinking after the current sequence is completed. The switch debounce delay is there to compensate for noise generated from the switch.
	void loop() {	if (digitalRead(ButtonPin)) {  // switch closed?	
	delay(40);                             // switch debounce delay	while (digitalRead(ButtonPin));        // wait for switch to open

    digitalWrite(RedLED, HIGH);            // switch red LED on
    delay(500);                            // leave LED on for 500ms
    digitalWrite(RedLED, LOW);             // switch LED off

    digitalWrite(GrnLED, HIGH);            // switch green LED on
    delay(500);                            // leave Green LED on for 500ms
    digitalWrite(GrnLED, LOW);             // switch LED off

    digitalWrite(BluLED, HIGH);            // switch blue LED on
    delay(500);                            // leave Blue LED on for 500ms
    digitalWrite(BluLED, LOW);             // switch LED off
    delay(500);                            // 500ms delay before loop begins again
    }
    else {
    // switch open with pull-down resistor
    digitalWrite(ButtonPin, LOW);           // switch LED off
    }
   }
### 8.) Uploaded code and it works as intended. It blinks through red, green, and blue. If I press and hold the button the blinking stops after it is done cycling through the colors
# Reflection
## 1. How long did it take you to complete this assignment?  
### About two hours including out of class 
## 2. What level of difficulty would you associate with this assignment?  
### Low 
## 3. If you associated medium/high difficulty with this assignment, what aspect did you find the most difficult?  
## 4. How comfortable do you currently feel with the course content?  
### Pretty comfortable
## 5. Do you have any additional information or feedback you would like to share with the instructors?
### N/A