

Problem number one.

The power supply for this printer is undersized. The power brich gets excessivly hot on long build and the voltage at the power inlet on the printer was measured to cosistanly drops from 12V to <10.5v to 11v. 

This is no so much a problem for the logic parts of the printer since there are voltage regulators for the ESP32 board and ARM processor logic circuits. There is no internal 12v regulator in the printer so the power brick is controlling the voltage to the steppers and the bed heater. There is no smoothing capacitor at the power entrance and there is only one 100uf 16v polarized cap on the system board. 

Please not that the colors red and black of wires on the jumper from the USB/Power board to the main baord are reversed on it appears most of these printers. The positive is marked on the board with a 

My Modifications.

I added 330uf 50v  polarized cap at jumper to the main board and a .1 uf ceramic cap for filtering.

After this the voltage measured at the jumper is 11.2v consistantly. The printer is less prone to stoppage due to power noise.


![pic](https://https://github.com/Mclute0/-MPMDv2-modifications-and-fixes/blob/main/pics/20220801_195936.jpg)



Problem number two.

The USB is cotrolled by a CD340G chip. The problem is with the interface design. The DTR pin of the CH340a is connected to the nRST pin on the ARM processor. This means that if the DTR is taken to ground or low, for whatever reason, the printer will reset. Connecting to the serial port duing a print may cause the printer to reboot and the print to fail. I believe that his is a bad design but may have been intended to provide a way to reboot during firmware upgrades. 

My initial soultion was to simply cut the DTR/nRST wire and I have no more uninteded reboots. I intend to install a 3 positiop toggel switch that could be used to reset the printer, return the DTR/nRST to the original configuration, or leave the connection open like I am running it now.
