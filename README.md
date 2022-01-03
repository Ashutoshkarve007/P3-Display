# P3-Display
P3 Led Display With Arduino

# Pin-Out

For Arduino uno

* A A0
* B A1
* C A2
* D A4
* R1 2
* R2 5
* B1 4
* B2 7
* G1 3
* G2 6
* LAT A3
* CLK 8
* OE 9
* GND GND

For Arduino Mega (Using Mega)

* A A0
* B A1
* C A2
* D A3
* R1 24
* R2 27
* B1 26
* B2 29
* G1 25
* G2 28
* LAT 10
* CLK 11
* OE 9
* GND GND



For Power just use a powerful enough 5v supply, these panels draw about 30W. I use a PC power supply.

# Library

Install Libraray

# Coding...

At first, you select a line to draw to via the 4 line select pins. They are in binary, ordered A B C D where a High means 1 and a low means 0. So for example for row 11 we would have A=1 B=1 C=0 D=1 (1+2+0+8 = 11). But now you might say: How is it possible to drive 32 rows with just 4 pins, which give only 2^4=16 options??

The answer lies in the fact, that there are actually two RED channel pins, two GREEN channel pins, and two BLUE channel pins, one for the upper half of the display, and one for the lower half.

Afterwards you have to set your RGB pins either on or off, then make the CLK pin go HIGH and LOW, and after a row full of led data you make the latch go HIGH LOW. You should also turn the OE(Output Enable) HIGH at some point in the line, it doesn't really matter where, I prefer the beginning.






# Reference

https://github.com/CamelCaseName/HUB75nano

https://create.arduino.cc/projecthub/CamelCaseName/running-a-32x64-rgb-led-panel-with-only-an-arduino-nano-c19385

[PxMatrix](https://github.com/2dom/PxMatrix)
