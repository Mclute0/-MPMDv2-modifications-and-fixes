
No version of Cura I have tried to use worked with the MPMDv2. Network printing does not work and USB printing does not work out of the box.

I found that the CH340g chip DTR pin is conneted to the nRST MCU of the main board. DTR (Data Terminal Ready) (DTR) is a control signal in RS-232 
serial communications, transmitted from data terminal equipment (DTE), such as a computer, to data communications equipment (DCE), 
for example a modem, to indicate that the terminal is ready for communications and the modem may initiate a communications channel.

The DTR signal is present on pin 20 of the 22-wire RS-232 interface using a DB-25 connector, and on pin 4 of a newer DE-9 serial port.
The signal is asserted (logic "1") by raising the voltage of the pin from negative to positive. 
Dropping the signal back to its negative state indicates to the modem that the communications session shall be terminated.

I found that when Cura was connecting via USB that the printer costantly rebooted. I played with the port settings in windows as there should be a way to change how DTR 
is being sent, however, I suspect it is being sent by Cura. 

This also show up win WiiBuilder if you opened a serial connection the printer would reboot.

Since the DTR signal is not critical to USB/uarts, I simply cut the DTR wire and suddenly I can print with any version of Cura via USB..

Here is a picture of the cut wire for refrence.

![pic1](/pics/DSCN0013.jpg)



