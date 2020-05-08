# ARDU-utilities
A easy-to-use command-line tool for flashing program or .hex files onto arduinos using a Raspberry Pi

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

## How to install:
1. Install arduino-mk and avrdude
2. Download and copy all 3 scripts into /usr/bin
3. Run chmod +x for all of them files

## How to use
1. Make a folder called "main" and go into it
2. Run "ard-config" to set everthing up
3. Write your programme in the file called main.ino
4. Run "ard-loader" to flash(this will erase the bootloader, so you can only programme the Arduino over the RPi GPIO, if you want to restore the Arduino, just flash a new bootloader on the Arduino using this software)

## How to preserve the bootloader(if it have one)
1. Instead running ard-loader as shown above, connect the Arduino to the RPi with USB only, and run ard-loader-usb

## Re-flashing the bootloader:
1. Create a new folder and go into it
2. Create another folder call build-uno
3. Put your bootloader in that folder
4. Go back the folder containing the build-uno folder
5. Run "ard-loader" to flash

## Troubleshooting:
1. If the ard-loader program can't find build-uno/main.hex, make sure you are in the folder where the Makefile and main.ino is, if you are, then try running this command "sudo mv build-uno/*.hex build-uno/main.hex" 
