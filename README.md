# Icom-CI-V
Source code for a digital VFO to appear as an Icom radio to PC applications

Any software which implements the virtual class "CatRadio()" contained in catradio.h
can be controlled from PC applications.

Tested with WSJT-X, Ham Radio Deluxe, flrig and fldigi.
Includes full support for PTT over CAT interface.

## Not all Icom interfaces are equal!
- Use "Icom 756Pro" unless otherwise specified.
- Use "Xeigu 5105" for flrig. (Version 1.3.51 or later)
- Try "Icom ic7000 or ic7200 after that.

Fldigi requires that you configure and save the settings, 
exit the program and then restart it.

WSJT works wonderfully with ic7000 setting.

## To use the code

- Inherit and implement the CatRadio() class.
- Create an instance of the IcomCI_V() class.
For example ````IcomCI_V mySerialInterface;````
Tell the serial interface about your radio. 
For example ````mySerialInterface.setRadio( (CatRadio*) &myRadio ) ;````
- call ````mySerialInterface.loop();```` periodically to read the serial port.
See Arduino "SerailEvent()" for a good place to call the .loop() method.

## Collaboration
Please share issues and fixes so others can benefit from your experience.
Thank you very much, Ed Taychert AA2MZ.
