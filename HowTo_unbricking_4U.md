
If you have bricked you printer you maye be able to fix it wit hthis information.


The MonoPrice MiniDelta v2 has two different processor. The main processor that handes the UI & newtoek is an ESP32-WROOM-32e with 4MB of memory. 
Ie can be flahsed manualy with the command line tools from EspressIF 

https://www.espressif.com/en/support/download/other-tools look for esptool.py documnetation.

The module is locaed under the front panel between the memory card and the touch screen. You DONOT need to disasemble the entire panel if you are smart about it.

Here is how..

here is the back of the main board...


![pic1](/pics/20220801_200219.jpg)

Note the yellow header pins on the lower left, on an unmodifies board they are plated throughholes and they are the all the connection needed to program the ESP32 module.

Here is the pin out lookin at the pin order as they appear in the picture. <br />
```xml
                               +-----+ <br />
   EN Enable esp32pin#3        | O O |  TX  esp32pin#35 <br />
   ground esp32pin#1,#15,#38   | O O |  RX  esp32pin#34 <br />
   vcc 3.3v esp32pin#2         | O O |  IO0 esp32pin#25 <br />
                               +-----+ <br />
  
.```
