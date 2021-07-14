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
