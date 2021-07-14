# UP11
## Introduction
In this documentation we will go through all the steps required to set up the prototype (revision 1) boards. 

## INDEX
* Power supply
* Power regulation
* Physical modified connections
* Setting up the arduino IDE to work with ESP 32
* Simple onboard test
* Testing the keypad
* Testing the NFC readers
* Testing the local implementation
* Testing the Flespi implementation

## Power supply
The input power to the board is supplied thourgh the barell jack.
The barell jack is configured as center positive as shown in the figure below
 ![barell jack config](https://github.com/Sasisekhar/UP11/blob/main/Pictures/1280px-Centre-positive.svg.png)
 
 This is how you would test if the barell jack is wired porperly:
  ![Barell jack test](https://github.com/Sasisekhar/UP11/blob/main/Pictures/check_powersupply.jpg)
 The positive lead on the interior and negative on the exterior
  
The input voltage can range from 5v to 16v. *Recommended input voltage is 12v*

Once you know that your barell jack is proper, you can proceed!

## Power regulation
Before plugging the powersupply into the barell jack, remove this jumper
![remove jumper](https://github.com/Sasisekhar/UP11/blob/main/Pictures/Remove%20jumper.jpg)

Once you've removed the jumper, power the board using the powersupply.
Once powered, use a multimeter in the voltage setting to measure the voltage across these 2 point:-
* The positive probe going to the bottom pin of the header (when the board is oriented in such a way that the NFC ports are at the top/ farthest from you and the keypad port is in the bottom/ closest to you)
* The negative probe goes to pin 3 (middle pin) of the voltage regulator
As shown in the figure:-
![test voltage](https://github.com/Sasisekhar/UP11/blob/main/Pictures/Test%20voltage.jpg)

The voltage reading should read between 5v and 9v ideally 7v.

You can adjust this voltage using the *DON'T ADJUST* potentiometer, but as the name suggests, **DO NOT ADJUST UNLESS ABSOLUTELY NECESSARY**

Once you're done you can move ahead to the next step!

