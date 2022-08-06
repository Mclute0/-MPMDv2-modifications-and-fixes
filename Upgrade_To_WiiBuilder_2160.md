
The version of WiiBuidler that ships with the MPMDv2 is Wiibuilder2.1.2.1 from Febuary 2021. 

The newer version have several more features including an auto-update function (not tested by me)

The the latest version of WiiBuilder can be downloaded from WeeDo3d at http://www.weedo.ltd/download-2/
you can use any version listed as far as I can tell, but you MUST edit the printer profile to have it recognize the MonoPrice pritner correctly.


Here is how I did it, other ways will problably work...

go into the directory

C:\Program Files (x86)\Wiibuilder2\data\profile\jsonProfile2

make a copy of the profile direcotry for the printer you are using, it should be appaent which one.

Uninstall WiiBuilder to be safe.

Instal the updated version of WiiBuilder that you downlaoded.

create a directory for the profile files can copy the files you backed up above into thisdir, I did 

C:\Program Files (x86)\Wiibuilder2\data\profile\jsonProfile2\MPMiniDeltaV2

navigate two level up to the driecotry

C:\Program Files (x86)\Wiibuilder2\data

edit the file

C:\Program Files (x86)\Wiibuilder2\data\machine.xml


at the beiniing just after 

<?xml version="1.0" encoding="utf-8"?>
<machines>

 --VVVVV-- copy the lines below into the machine.xml file save and you should be able to open WiiBuilder and select the MiniDelta v2 as a printer --VVVVVVV--
```xml
  
  <machine experimental="0">
		<name>MP Mini Delta V2</name>
		<geometry type="cartesian">
			<!-- different pulleys on X and Y axii -->
			<axis id="x" length="110" maxfeedrate="9000" homingfeedrate="1200" stepspermm="94.139704" endstops="max" timeout="60"/>  <!-- Pulley dia: 10.82mm / 1/8 step = 1/(10.82 * pi / 1600) -->
			<axis id="y" length="110" maxfeedrate="9000" homingfeedrate="1200" stepspermm="94.139704" endstops="max" timeout="60"/>  <!-- Pulley dia: 10.82mm / 1/8 step = 1/(10.82 * pi / 1600) -->
			<axis id="z" length="120" maxfeedrate="240" homingfeedrate="1100" stepspermm="400" endstops="min" timeout="60"/> <!-- Actual length is 157mm, we reserve ~5mm for safety.TR-8x8 Z axis = 1/(8/1600) -->
			<axis id="a" length="100000" maxfeedrate="1600" stepspermm="94.139704" endstops="none" homingfeedrate="1100" timeout="60"/> <!-- stepspermm is incoming filament length, see comment at bottom for explanation -->
		</geometry>
		<tools>
			<tool name="Mk8" stepper_axis="a" index="0" type="extruder" motor="true" fan="true" heatedplatform="true" motor_steps="3200" default_rpm="3" heater="true"/>
		  <extruderCount>1</extruderCount>		
    </tools>
    <bedShape>circular</bedShape>
    <wlan>
        <type>WiFiCam</type>
        <camera>false</camera>
    </wlan>
    <thumbnail>
        <visible>true</visible>
        <size>140</size>
        <rotateAngle>0</rotateAngle>
        <type>sjpeg</type>
    </thumbnail>
    <preheat>true</preheat>
    <meterials>m_pla,m_abs,m_tpu,m_other</meterials>
		<clamps></clamps>
		<driver name="RepRap">
			<!-- optional: <portname>COM3</portname> -->
			<rate>115200,57600</rate>
            <flipAxis></flipAxis>
		</driver>
		<warmup>
		</warmup>
    <firmwareFlavor>RepRap (Marlin/Sprinter)</firmwareFlavor>
	<printerCenter>0,0</printerCenter>
		<cooldown>
				M18 (Turn off steppers after a build.)
		</cooldown>
    <appendGcode>
      <startCode></startCode>
      <endCode></endCode>
    </appendGcode>
</machine>
.```
 





