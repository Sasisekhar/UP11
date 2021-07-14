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
 ![barell jack config](https://upload.wikimedia.org/wikipedia/commons/thumb/8/84/Centre-positive.svg/1280px-Centre-positive.svg.png)
 
 This is how you would test if the barell jack is wired porperly:
  ![Barell jack test](https://itp.nyu.edu/physcomp/wp-content/uploads/check_powersupply.jpg)
  The positive lead on the interior and negative on the exterior
  
The input voltage can reange from 5v to 16v. *Recommended input voltage is 12v*
