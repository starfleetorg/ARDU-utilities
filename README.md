# ARDU-utilities
A easy-to-use command-line tool for flashing programmes or .hex files onto arduinos using the GPIO pins of a Raspberry Pi

## Dependencies:
1. Avrdude
2. Arduino-mk

## Connecting the devices:
1. GPIO(BCM) to Arduino connections
2. GPIO 8  ==>  Arduino reset(RES)
4. GPIO 11  ==>  Arduino digital 13
5. GPIO 9  ==>  Arduino digital 12
6. GPIO 10  ==>  Arduino digital 11
8. GPIO GND  ==>  Arduino GND
9. Make sure that the Arduino is powered

## How to use:
0. Install arduino-mk and avrdude
1. Download and copy both scripts into /usr/bin
2. Run chmod +x for both files
3. Make a folder and go into it
4. Run "ard-config" to set everthing up
5. Write your programme in the file called main.ino
6. Run "ard-loader" to flash(this will erase the bootloader, so you can only programme the Arduino over the RPi GPIO, if you want to restore the Arduino, just flash a new bootloader onth the Arduino using this software)

## Re-flashing the bootloader:
1. Create a new folder and go into it
2. Create another folder call build-uno
3. Put your bootloader in that folder
4. Go back the folder containing the build-uno folder
5. Run "ard-loader" to flash

## Troubleshooting:
1. If the ard-loader programme can't find build-uno/main.hex, make sure you are in the folder where the Makefile and main.ino is, if you are, then try running this command "sudo mv build-uno/*.hex build-uno/main.hex" 
