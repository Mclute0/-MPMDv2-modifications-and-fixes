
If you have bricked you printer you maye be able to fix it wit hthis information.


The MonoPrice MiniDelta v2 has two different processor. The main processor that handes the UI & newtoek is an ESP32-WROOM-32e with 4MB of memory. 
Ie can be flahsed manualy with the command line tools from EspressIF 

https://www.espressif.com/en/support/download/other-tools look for esptool.py documnetation.

The module is locaed under the front panel between the memory card and the touch screen. You DONOT need to disasemble the entire panel if you are smart about it.

Here is how..

here is the back of the main board...


![pic1](/pics/20220801_200219.jpg)

Note the yellow header pins on the lower left, on an unmodifies board they are plated throughholes and they are the all the connection needed to program the ESP32 module.

Here is the pin out lookin at the pin order as they appear in the picture.

      O O 
      O O
      O O
