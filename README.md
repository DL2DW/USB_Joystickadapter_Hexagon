# USB Joystickadapter from Hexagon (SMD Version)

![](https://github.com/DL2DW/USB_Joystickadapter_Hexagon/blob/main/Images/USB_Joystickadapter_Hexagon_PCB_assembled.jpg)

I found the documentation and firmware for this joystick adapter on the website http://www.hexagons.de/index.php/USB_Joystickadapter some time ago. This is no longer available online for a long time.

It is a joystick adapter with 2 ports for the known DB9 connectors, as they are used with the Atari, or Commodore joysticks. 

This adapter can be connected to a PC or the well known MiSTer FPGA hardware, and so the old homecomputer joysticks can be used on modern hardware.



## "Sinchai" version

![](https://github.com/DL2DW/USB_Joystickadapter_Hexagon/blob/main/Images/Sinchai_Version.jpg)

There is also a version that is built with normal THT components. This was once sold in a store, but it no longer exists.

And I could not find a suitable case for Hexagon's version. So I packed the hardware into an existing case with the help of a newly developed circuit board.



## Assembly

Under the article number "COM 943" there is a housing at the electronics mail order company Reichelt from Germany ( https://www.reichelt.de/selbstbaugehaeuse-d-sub-2x-9-pol-metallisiert-com-943-p161.html?&nbc=1 ), in which two 9pin D-SUB sockets fit wonderfully. You only have to drill a small hole for the USB cable.

The board is equipped with SMD components to save space. Whereby I have worked here with parts as large as possible, so that on SMD beginners could assemble this board without problems.

The assembly is actually quite simple, since only a few components are needed. The components are assembled from small to large. First the resistors, then the capacitors, followed by the quartz. Then the programmable microcontroller.

Finally the pin header, which is needed to program the microcontroller and the two DB9 connectors. Here I recommend to put the construction together first by hand and to solder it into one half of the case. Then solder the first side of the DB9 sockets to the board. And then the back side can be soldered.

Then a small hole must be drilled in a bottom part of the adapter in the side, so that the USB cable can be put through there. It is best to take a ready-made cable with an open end. Such cables are available at Reichelt.

After passing the cable through the previously drilled hole, the wires can be soldered to the board. To secure the cable from being pulled out, a small cable tie should be pulled around the cable.



![](https://github.com/DL2DW/USB_Joystickadapter_Hexagon/blob/main/Images/USB_Joystickadapter_Hexagon_3D.png)



When everything is assembled, the adapter should look like this.



![](https://github.com/DL2DW/USB_Joystickadapter_Hexagon/blob/main/Images/USB_Joystickadapter_Hexagon_with_case.jpg)



## Flashing the firmware

Now only the microcontroller must be flashed with the appropriate firmware. This can be done most simply with the tool avrdude. The call differs of course, depending on the used programming adapter a little bit. For the very popular and widely used USBASP adapter the whole thing would look like this:

**avrdude -c usbasp -p t4313 -U flash:w:main4313.hex -U lfuse:w:0xcf:m -U hfuse:w:0xdb:m -U efuse:w:0xff:m** 



## BOM

Here is the list of components. 

- 2x 100nF capacitor / 0805
- 1x 10µF tantalum capacitor / Kemet B
- 2x 22pF capacitor / 0805
- 2x Zener diode BZT52C3V6 / SOD 123
- 1x Littlefuse1206L150THWR / 1206
- 2x DB9 female, male with solder cups
- 1x 10k resistor 1/8W, 1% / 0805
- 1x 1.5k resistor 1/8W, 1% / 0805 
- 2x 68 resistor 1/8W, 1% / 0805 
- 1x ATTiny 4313-SU / SOIC-20W
- 1x 12MHZ crystal / 5032, 2pin
- header 2 rows
- USB connection cable



## PCB

The PCB can either be ordered directly from [PCBWay](https://www.pcbway.com/project/shareproject/USB_Joystickadapter_from_Hexagon__SMD_Version_.html), or you can create it yourself from the Gerber files available here.

[![PCBWay](https://www.pcbway.com/project/img/images/frompcbway.png)](https://www.pcbway.com/project/shareproject/USB_Joystickadapter_from_Hexagon__SMD_Version_.html)



If you liked my project, I would be very happy about a small coffee donation.

[![ko-fi](https://www.ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/R6R62T6RN)



# License

The contents of this repository, with the exception of the Firmware directory, are released under the following license:

- the "Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License" (CC BY-NC-SA 4.0) full text of this license is included in the [LICENSE.CC-NC-BY-SA-4.0](https://github.com/DL2DW/TriMod_Adapter_SMD_Version/blob/main/LICENSE.CC-NC-BY-SA) file and a copy can also be found at https://creativecommons.org/licenses/by-nc-sa/4.0/

