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
Initial tests completed and the board works properly. All MOSFETs open fully, all motor controllers step properly, and all endstops read properly, with both mechanical and Hall-Theta sensors. Watch the test here: http://youtu.be/WANil9Fsz-o

Assembly Hints
--------------
The small pitch of the chips require reflow. I recommend first attaching the FETs, resistors, capacitors, and level shifter and reflowing, following with desoldering braid to fix inevitable bridges. After the ICs are properly attached, you can add the through-hole headers. Note that on J6 (the 16x2 header) the top edge closest to the SM 2x2 header needs to be sanded down a bit so that the 2x2 and the 16x2 fit close enough together. Once the through-hole headers are attached, place the SM pins into the Due (or a Mega) and place the board on top. The through-hole pins will act as aligners so that the SM pin legs should be over the pads on the board. Solder all the pins you can reach, and then CAREFULLY remove the board from the Arduino, and get the inside legs. Repeat similarly with the female headers in the RAMPS. Upon completion, test it out. Note that for the gates to work properly, the RAMPS needs to be connected to 12V and needs to have the diode D1 installed; that 12V is utilized by the Ramps2Due MOSFETs to open the RAMPS MOSFETS.
