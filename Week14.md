# Weekly activities:

## ECSE 395 
## 4/14/25

Robert and I 3D printed our bowl prototype. It's worth noting that it's printed in PLA, which was not ideal since we wanted PETG or ABS, but it's good enough. 

I worked on creating some battery life projections and statistical graphs. Attached are the pictures of those calculations, which assume no power loss from the MP buck voltage regulator that we're using. We're also assuming that it will be powered on for 16 hours per day, with 8 hours a day set aside for deep sleep mode, effectively zero power draw. Even so, my calculations at best show about a week long of battery life, even when the LEDs are 70/255 brightness (where 255 is max brightness).

But I started to experiment with light sleep mode for the minimum power draw. My initial readings show a nominal power draw of around 6mA, which is about 1/10 of the regular nominal power draw. Also, our LEDs + weight sensor should still work. This would massively increase battery life. I will do those calculations in the future. 

As for the weight sensor, it arrived and I soldered them to an HX711 board in order to decode the readings. The readings were still garbled but it seems to reliable output a signal, so we're hoping that it will work when we assemble it. 

Joseph created a github for us to contribute to with the ESP32 code. Joseph finished our study design and we're recruiting our classmates. Prof. Block said that we should recruit more than 10 people and each person has 4 tests. 8 people in class and 8 out of class. Plus we have a singular cat that we would like to test with. The tests will mainly consist of analyzing whether or not it's obvious how full the bowl is. 

![](Ecse%20395_250414_115143_1.jpg)
![](Ecse%20395_250414_115143_2.jpg)
![](Ecse%20395_250414_115143_3.jpg)
![](Ecse%20395_250414_115143_4.jpg)![](Ecse%20395_250414_115143_5.jpg)