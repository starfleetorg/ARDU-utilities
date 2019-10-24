# ARDU-utilities
A easy-to-use command-line tool for flashing programmes or .hex files onto arduinos using the GPIO pins of a Raspberry Pi

## Connecting the devices:
1. GPIO(BCM) to Arduino connections
2. GPIO 8  ==>  Arduino reset(RES)
4. GPIO 11  ==>  Arduino digital 13
5. GPIO 9  ==>  Arduino digital 12
6. GPIO 10  ==>  Arduino digital 11
8. GPIO GND  ==>  Arduino GND
9. Make sure that the Arduino is powered

## How to use:
1. Download and copy both scripts into /usr/bin
2. run chmod +x for both files
3. make a folder and cd into it
4. run "ard-config" to set everthing up
5. run "ard-loader to flash"(this will erase the bootloader, so you can only programme the Arduino over the RPi GPIO, if you want to restore the Arduino, just flash a new bootloader onth the Arduino using this software)

## Re-flashing the bootloader:
1. Create a new folder and cd into it
2. Create another folder call build-uno
3. Put your bootloader in that folder
4. go back the folder containing the build-uno folder
5. Flash the bootloader just like any other programmes you flash before with this tool
