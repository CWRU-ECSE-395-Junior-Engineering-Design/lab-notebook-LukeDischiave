# Weekly activities:

## ECSE 395 
## 4/14/25

We are fixing our weight sensor, and we have our 3d printed bowl now. 

set up the github so we can contribute to teh code at the same time. 

going to add the lightsleep code to your code after joseph is finished with calibrating the weight sensors. 

need to drill holes in the bowl in order for the LEDs to pop through

need to sand the edges of the bowl because they are too sharp

the factor of the weights needs to be really precise, since they're designed for 50kg and we have 4 of them and they are not measuring nearly that much weight. 
there might also be a minimum weight of aaround half a kilogram.

in terms of the weight sensors, they are too small to fit directly below the bowl. 
we are planning on platforming the bowl in order to fit them all, since it's a prototype this is acceptable. 

now we decided to desolder teh 3 weight sensors and just use one, with two 1k resistors. \


polling rate of our code should be pretty low since it doesn't need to update all the time

update 4/16: trying with one weight sensor, it's even more broken than the 4 sensors in a wheatstone bridge. we are going to instead go with a wizard of oz technique for our user study, since we wont be able to figure out what's wrong before friday. before then, I will be assembling the prototype sans the weight sensor. 

I also figured out that light sleep mode does not have enough functionality, as it pauses the CPU and prevents it from running new code. 

Power saving summary:
In order to save the most power while we run our code, I have developed modem sleep code, which limits CPU frequency to 40MHz and turns off wifi and bluetooth. this will run 24/7.

Light sleep pauses and resumes the CPU, so we can't use this because it will also pause the timer. We want the timer to resume

Deep sleep completely turns off and restarts the esp32. Needless to say, we don't want this. 

I plan on assembling this prototype today and tomorrow with my free time. 

Final prototype: 3 way switch: middle is off, left + right are food/water, switch to reset timer





