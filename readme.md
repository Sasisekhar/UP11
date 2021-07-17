# UP11
## Introduction
In this documentation we will go through all the steps required to set up the prototype (revision 1) boards. 

## INDEX
* Power supply
* Power regulation
* Physical modified connections
* Setting up the arduino IDE to work with ESP 32
* Cables
* Simple onboard test
* Testing the keypad
* Testing the NFC readers
* Testing the local implementation
* Testing the Flespi implementation

## Power supply
The input power to the board is supplied thourgh the barrel jack.
The barrel jack is configured as center positive as shown in the figure below
 ![barrel jack config](https://repo.true2air.com/True2Air/ESPAssetController/raw/branch/master/Pictures/1280px-Centre-positive.svg.png)
 
 This is how you would test if the barell jack is wired porperly:
  ![Barrel jack test](https://repo.true2air.com/True2Air/ESPAssetController/raw/branch/master/Pictures/check_powersupply.jpg)
 The positive lead on the interior and negative on the exterior
  
The input voltage can range from 5v to 16v. *Recommended input voltage is 12v*

**If however you do not have a barell jack:-**

Strip the ends of the power cable to expose the positive (red) and negative (black) wires.

The red and black wires have to be soldered on as shown in the figures :
<img src="https://github.com/Sasisekhar/UP11/blob/main/Pictures/plus%20minus%20bottom.jpg?raw=true" style="height: 5px width:5px"/>
![Soldered wires](https://github.com/Sasisekhar/UP11/blob/main/Pictures/Red%20and%20black.jpg?raw=true)

Once soldered, you can move on to the next step!
## Power regulation
Before plugging the powersupply into the barell jack, remove this jumper
![remove jumper](https://github.com/Sasisekhar/UP11/blob/main/Pictures/Remove%20jumper.jpg?raw=true)

Once you've removed the jumper, power the board using the powersupply.
Once powered, use a multimeter in the voltage setting to measure the voltage across these 2 point:-
* The positive probe going to the bottom pin of the header (when the board is oriented in such a way that the NFC ports are at the top/ farthest from you and the keypad port is in the bottom/ closest to you)
* The negative probe goes to pin 3 (middle pin) of the voltage regulator
As shown in the figure:-

![picture](https://repo.true2air.com/True2Air/ESPAssetController/raw/branch/master/Pictures/Test%20voltage.jpg)
The voltage reading should read between 5v and 9v ideally 7v.

You can adjust this voltage using the *DON'T ADJUST* potentiometer, but as the name suggests, **DO NOT ADJUST UNLESS ABSOLUTELY NECESSARY**

Once you're done you can move ahead to the next step!
# **NEVER PLUG THE 12v SUPPLY AND THE 5v USB AT THE SAME TIME**
## Physical modified connections
Check behind the board to ensure that all the modifications made are still secure and have not come loose. The wires going to the NFC modules might seem slightly flimsy, but that is by design.

Once you've done confirming that all connections are steady, move ahead to the next step!

## Setting up the arduino IDE to work with ESP 32

- ***Step 1:*** Go to this [link](https://www.arduino.cc/en/software) and download the latest version of the arduino IDE
- ***Step 2:*** In your Arduino IDE, go to **File > Preferences**

![files > preferences](https://i2.wp.com/randomnerdtutorials.com/wp-content/uploads/2016/12/arduino-ide-open-preferences.png?w=196&quality=100&strip=all&ssl=1)

- ***Step 3:*** Enter https://dl.espressif.com/dl/package_esp32_index.json into the “Additional Board Manager URLs” field as shown in the figure below. Then, click the “OK” button:

![Adding field](https://i0.wp.com/randomnerdtutorials.com/wp-content/uploads/2018/06/preferences.png?w=722&quality=100&strip=all&ssl=1)

- ***Step 4:*** Open the Boards Manager. Go to **Tools > Board > Boards Manager**

![Boards manager](https://i2.wp.com/randomnerdtutorials.com/wp-content/uploads/2018/06/boardsManager.png?w=628&quality=100&strip=all&ssl=1)

- ***Step 5:*** Search for ESP32 and press install button for the “ESP32 by Espressif Systems“:

![ESP32](https://i1.wp.com/randomnerdtutorials.com/wp-content/uploads/2018/06/installing.png?w=786&quality=100&strip=all&ssl=1)

- ***Step 6:*** Plug the ESP32 board to your computer. With your Arduino IDE open
- ***Step 7:*** Select your Board in **Tools > Board** menu (in our case it’s the ESP32 DEVKIT V1)

![](https://i2.wp.com/randomnerdtutorials.com/wp-content/uploads/2016/12/windows-select-board.png?w=614&quality=100&strip=all&ssl=1)

- ***Step 8:*** Select the Port

![](https://i0.wp.com/randomnerdtutorials.com/wp-content/uploads/2018/08/com-port-selected.jpg?w=687&quality=100&strip=all&ssl=1)

- ***Step 9:*** Open the following example under **File > Examples > Basics > Blink**

![](https://github.com/Sasisekhar/UP11/blob/main/Pictures/Blink.jpg)

- ***Step 10:*** change the line `int led = 13;` to `int led = 2;`

![](https://github.com/Sasisekhar/UP11/blob/main/Pictures/Blink_1.jpg)

- ***Step 11:***  Press the Upload button in the Arduino IDE. Wait a few seconds while the code compiles and uploads to your board.

![](https://i0.wp.com/randomnerdtutorials.com/wp-content/uploads/2016/12/arduino-ide-upload-button.png?resize=34%2C29&quality=100&strip=all&ssl=1)

- ***Step 12:*** Looking at the bottom part of the IDE, as soon as it says `Connecting ...___...` press the `BOOT` button on the ESP32

![](https://github.com/Sasisekhar/UP11/blob/main/Pictures/Connecting....jpg)

- ***Step 13:*** As soon as it continues from `Connecting...___` you can release your finger
- ***Step 14:*** If everything went as expected, you should see a “Done uploading.” message and a blue LED should be blinking on the board.

![](https://i0.wp.com/randomnerdtutorials.com/wp-content/uploads/2016/12/windows-arduino-ide-done-uploading.png?w=671&quality=100&strip=all&ssl=1)

*Done!* You have successfully uploaded firmware onto the ESP32! Now, whenever you have to upload firmware, all you have to do is that the **Tools > Board** and the Port is selected properly and you're set to go!

## Cables
There are three cables provided in the box; two 8 wired cables and one 9 wired cable. The 9 wired cable has a 90 degree connector on either end.

The 90 degree connector is for the keypad while the other 2 connectors are for the NFC readers

The keypad cable can only be connected to the keypad a certain way, while on the PCB end, the white end of the ribbon cable should go to the pin that has the yellow wire under it; so, White wire -> Yellow wire

The cable configuration for the NFC readers are as such:-
   - White wire on the ribbon cable -> Pin which has yellow wire on the bottom
   - Brown wire on the ribbon cable -> The arrow on the NFC reader

By arrow on the NFC reader, I mean this:-

![NFC ARROW](https://github.com/Sasisekhar/UP11/blob/main/Pictures/NFC_Arrow.jpg?raw=true)

And as the silkscreen on the board suggests,the 2 NFC connectors are labelled as *NFC_1* and *NFC_2*, while the connector for the keypad is named as *KEYPAD*

With this all the setup required for running tests is done!

## Tests
### Getting all the libraries setup
1. **PubSubClient (MQTT)**
- Download the library from https://github.com/knolleary/pubsubclient and extract it to **Documents/Arduino/libraries** as **PubSubClient**
- Ensure that the folder contains the following:
  - Three folders names *examples*, *src* and *test* respcteively
  - Readme file
  - keywords file
  - library json file
- The above mentioned files and folders should be directly in the *PubSubClient* folder itself; ensure that there isn't a PubSubClient-master folder within the *PubSubClient* folder

![File system](https://github.com/Sasisekhar/UP11/blob/main/Pictures/PubSubClient.jpg?raw=true)


2. **Adafruit-PN532 library (NFC)**
- Open the Arduino IDE and go to **Tools -> Manage Libraries**
- In the dialog box that appears, type *PN532* in the search bar and press enter
- Find the *Adafruit PN532* entry and install the latest version
![PN532](https://github.com/Sasisekhar/UP11/blob/main/Pictures/PN532.jpg?raw=true)

### Testing the Keypad, LEDs and the Solenoid
***THE BARREL JACK SHOULD BE REMOVED WHEN PROGRAMMING***
- Open the **KEY_TEST.ino** file and upload it onto the ESP32 according to the instructions given above
- Connect the Red and Green LEDs to the connectors coming from **RED** and **GREEN** respectievely
- Connect the solenoid to the connector coming from **SOL**
- Connect the Keypad
- Once all the connections have been completed, remove the micro USB cable and plug the barrel connector in
- Once powered, the Red LED and the backlight of the keypad must be lit.
- Entering the code *4817* must turn off the Red LED, turn on the Green LED and open the Solenoid for 5 seconds
- After a duration of 5 seconds, everything returns to the original state

### Testing the PN532
***THE BARREL JACK SHOULD BE REMOVED WHEN PROGRAMMING***
***THE BARREL JACK IS NOT REQUIRED FOR THIS EXAMPLE***
- Open the Arduino IDE
- Open **NTAG_TEST.ino** and upload it onto the ESP32 (Instructions above; don't forget to use the correct port)
- Open the serial monitor by clicking this icon present on the top right corner of the IDE

![Serial monitor](https://github.com/Sasisekhar/UP11/blob/main/Pictures/Serial%20monitor.jpg?raw=true)

- Once the Serial monitor opens up, go to the bottom right corner and change the Baudrate to *115200 baud* (It is set to *9600 baud* by default)

![Baud](https://github.com/Sasisekhar/UP11/blob/main/Pictures/Baud.jpg?raw=true)

- Connect the NFC reader to **NFC_1** on the board according to the wiring instructions given above
- Once everything is ready, press the *EN* button on the ESP32
- Bring the NFC tag close to the NFC reader while obesrving the Serial monitor
- You should see the UUID etc of the NTAG being printed on the Serial monitor
- Voila! You're done!
