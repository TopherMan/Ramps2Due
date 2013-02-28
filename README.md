Overview
========
This is a converter board allowing a RAMPS 1.4 to be plugged into an Arduino Due. Additionally, since the Due has moved the MOSI/MISO to the SPI pins and the SD RAMPS card has integrated level shifters that are no longer necessary, it will integrate a simple SD card reader.
This is based on bobc's RIB found [here](https://github.com/bobc/bobc_hardware/tree/master/RAMPS-FD).

Features
--------
For full details on the differences between the Mega and the Due, see [here](http://reprap.org/wiki/RAMPS-FD).
This board will make the following conversions:
- VCC on RAMPS (5V) will connect to 3V3 on Due
- All endstop and UART pins will be passed through a level shifter, allowing mechanical, optical, or Hall sensors for endstops
- Add signal MOSFETs to be sure the RAMPS MOSFETs are fully open
- Since all VCC on RAMPS needs to be 3.3V, add a 5V pin (or pins?) for any endstops or similar that require 5V to power

NB
--
Please note that this is not yet tested. This readme will be updated once testing has been done, so if you still see this message, assume that the current board will break your precious Due.
