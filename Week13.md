# Weekly activities:

## ECSE 395 
## 4/4/25

Robert is working out the logistics for how the battery pack and breadboard are going to fit into the cat bowl he bought at the store, which we are using. He started to design the table that will raise the cat bowl in CAD. We plan on meeting at thinkbox next week to continue this. 

We finalized some ideas for powering our prototype. We are going to use 5 AA alkaline batteries in series to get ~8V. Then, we will have it connected to a buck voltage regulator to minimize power loss. We also want to keep the option of using a 9V battery open to the stakeholder.

Joseph created a Github for us to contribute to. He also started to program the prototype. He's starting to design the study for our prototype now. 

I measured the current of the ESP32 with 4 LEDS fully on and at around 30% brightness using the Sears lab equipment. Then, I measured the current with no LEDs (or anything connected to the ESP32) to find our nominal current draw. I still have yet to measure the current draw for when the ESP32 is in deep sleep mode and when it's in light sleep mode. Overall, these measurements are all to ensure that we are optimizing battery life. 
## 4 LED full brightness current draw ~160-170mA
![](Pasted%20image%2020250404150929.png)

## 4 LED 70/255 brightness current draw ~92mA
![](Pasted%20image%2020250404151047.png)

## No LED nominal current draw ~68-69mA
![](PXL_20250404_124648756.jpg)

So clearly, reducing the brightness has netted significant energy savings, almost 50%!