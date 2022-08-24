# LCD-screen-Backlight-LED-External-control-circuit

The present circuit is a PCB design based on the original concept published by Georg Keller (FMI Basel) and implemented by Martyn Stopps (NIMR, London & SWC) to optimize footprint and production. This work is only the implementation of the circuit in to a small PCB and a new version generating an inverting output that can be embedded inside of the original screen enclosure. The circuit provides the synchronization between each frame on the microscope acquisition and the flickering frequency of the screen back-illumination. The digital signal to the LED of the Toshiba photocoupler is generated in the two-photon acquisition software (ScanImage) from a modified line clock synchronized to the scanner DAQ board. This signal is transmitted to each of the four LED panels of the LCD display generating the desired current through the LED drivers BCR 421U E6327. The photocoupler also isolates the 5V control circuit from the 48V power circuit. The output current is modulated with an external resistor (Rext), in parallel with the Rint of the LED driver.

![alt text](https://github.com/FrancisCrickInstitute/LCD-screen-Backlight-LED-External-control-circuit/blob/main/Schematic.png?raw=true)
![alt text](https://github.com/FrancisCrickInstitute/LCD-screen-Backlight-LED-External-control-circuit/blob/main/Figures/LED%20Driver%20Picture.png?raw=true)

Application example
In the two-photon microscopes we worked with, every line in bidirectional scanning mode takes 62.5 us and we usually image for ~48 us. So that leaves us with ~14.5 us to turn on the monitor.

![alt text](https://github.com/FrancisCrickInstitute/LCD-screen-Backlight-LED-External-control-circuit/blob/main/Experimental%20data/tek0000.png?raw=true)
![alt text](https://github.com/FrancisCrickInstitute/LCD-screen-Backlight-LED-External-control-circuit/blob/main/Experimental%20data/tek00000.png?raw=true)


Rext selection criteria

The Value of the resistor associated on the output depends on the current demanded for your monitor/your brightness requirements. The screens we tested operate at 55-75 mA per channel. We recommend to measure these parameters in normal conditions and then choose the adequate Rext value according to the following figure from the Infineon BCR 421U datasheet.

Models of monitor tested

	Dell U2415 (48Vdc, Iout = 72 mA , Rext = 12R)

The instructions on how to install it inside the Dell display are i the Documentation file.
