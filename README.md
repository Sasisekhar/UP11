# UP11
## Introduction
In this documentation we will go through all the steps required to set up the prototype boards

> INDEX
> * Power supply
> * Power regulation
> * Physical modified connections
> * Setting up the arduino IDE to work with ESP 32
> * Simple onboard test
> * Testing the keypad
> * Testing the NFC readers
> * Testing the local implementation
> * Testing the Flespi implementation

## Power supply
The input power to the board is supplied thourgh the barell jack.
The barell jack is configured as center positive; i.e. the outer jacket is negative and the internal contactis positive (**ENSURE THAT THE CONNECTOR IS THE SAME**)
 ![barell jack config](https://upload.wikimedia.org/wikipedia/commons/thumb/8/84/Centre-positive.svg/1280px-Centre-positive.svg.png)
The input voltage can reange from 5v to 16v. Recommended input voltage is 12v
