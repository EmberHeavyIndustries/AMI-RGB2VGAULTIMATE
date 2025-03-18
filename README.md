# AMI-RGB2VGAULTIMATE
The Ultimate Double buffered, Impedance matched, User selectable filtered NO-VERTICAL_BARS RGB to VGA adapter for all Amigas


**If you like this project and want to contribute to its further development, please consider donate some $ or € (paypal friends & family, please or DO NOT select "Buying something" from money transfer frontpage).** 

| [![paypal](https://www.paypalobjects.com/en_US/i/btn/btn_donateCC_LG.gif)](https://paypal.me/mrkbrr)||[![Email, Contacts & Requests](https://github.com/EmberHeavyIndustries/Depot/blob/master/Pics/EmailSticker.jpg?raw=true)](mailto:EmberHEavyIndustries@gmail.com)|
| ------------------------------ | ---------------------------------------------- | --------------------------- |


[![License: CC BY-NC-SA 4.0](https://img.shields.io/badge/License-CC%20BY--NC--SA%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc-sa/4.0/)

# Shared project on a builder's site

From time to time small batches could be available on sale on Amibay here:

[Amibay project page]([https://www.pcbway.com/project/shareproject/AMIRGB2VGA_ULTIMATE_6bd4d0e4.html

[PCBWAY's project page](https://www.pcbway.com/project/shareproject/AMIRGB2VGA_ULTIMATE_6bd4d0e4.html)

![Image of RGB2VGA2-02](https://github.com/EmberHeavyIndustries/AMI-RGB2VGAULTIMATE/blob/main/Docs/RGB2VGAV3_01_300.jpg)
![Image of RGB2VGA2-03](https://github.com/EmberHeavyIndustries/AMI-RGB2VGAULTIMATE/blob/main/Docs/RGB2VGAV3_02_300.1.jpg)

# AMI-RGB2VGAULTIMATE is a **"revised-revised" RGB to VGA adapter** for the Amiga A500-A600-A2000 and A1200-A4000, with unique improvements:

- Fully buffered Composite HSync and VSync signals
- Selectable CSync signal for those lucky guys who own a Sony PVM monitor
- Impedance matched inputs and outputs
- Fully high quality buffered video signals
- Fully filtered spurious input frequencies: no more vertical bars on LCD screens !
- Four user selectable filter settings: precisely match your display resolution for perfect quality !
- Smaller than the original 390682-01/03 VGA dongle by commodore

# THE ISSUE

When connecting an Amiga computer (or in general any computer/console designed to be used with an analogue RGB monitor) to a modern LCD screen with a VGA interface, one can observe the typical 'jail bars', annoying horizontal stripes covering the entire screen.

The VGA input , unlike the scart one, is not bandwidth limited in any way; thus it picks up any spurious noise on the Amiga RGB signals.

More in detail, the basic problem is the VGA monitor: the Amiga video output was designed with CRTs in mind (which was the correct solution at the time); the video bandwidth of those CRTs was something limited to ~10MHz.

Video jailbars artifact are, in the frequency domain, frequency components >28MHz (they come from the fundamental Amiga 28Mhz clock and its higher harmonics) .

Modern VGA/LCD displays, support today video bandwidths of 130MHz and more, so they are able to display these frequency components which take the form of annoying jail bars.

# THE SOLUTION

A practical and effective solution to the issue is to limit the video bandwidth from the source with a proper video amplifier chip with lowpass filter.

The cut-off frequency of the low-pass filter must be correctly calculated in order to eliminate unwanted frequencies, without however compromising the quality and definition of the video information to be displayed.

In the case of the Amiga series computers, it is basically a matter of calibrating the filters for two major cases: OCS/ECS and AGA.
In the first case, filtering calibrated at 9Mhz or 18Mhz is appropriate, while in the second case it is appropriate to increase the bandwidth, filtering around 30Mhz.

The design described here combines in one device the ability to select any of four appropriate cut-off frequencies on the fly, using a commercial chip from Texas Instruments, which performs the function of video amplifier and selectable filter.

The inputs and outputs of the circuit are also calibrated to the correct impedance of the video signals, and the horizontal and vertical synchronisation signals are buffered for maximum possible stability.

Finally, an option has been included to replace the horizontal synchronisation signal with the composite synchronisation signal, so that Sony PVM-type displays or GBS-C-type converters can be connected.

A few other passive components and the necessary VGA (to monitor) and DB-23 (to Amiga) connectors complete the design.

The latter connector, rather rare nowadays, can be purchased from various Chinese suppliers, or made from a common DB-25 connector by simply removing the two outermost pins.

Each video component (R, G, B) is processed according to the following principle scheme:

![Principle](https://github.com/EmberHeavyIndustries/AMI-RGB2VGAULTIMATE/blob/main/Docs/1.png)

The switchable frequency lowpass filter show the following figures:

![Filters](https://github.com/EmberHeavyIndustries/AMI-RGB2VGAULTIMATE/blob/main/Docs/2.png)


# NOTE for users:

User can freely select any of the four lowpass filter profiles, to either match SD, ED, HD or FHD resolutions for maximum clarity and cleaness
Refer to the table on the back of the pcb for SW1 switch settings code.

Further option is to switch between HSync and CSync for Sony PVM lucky users needs.
Looking the board from above, with DB23 connector on your left, settings are:
  - Switch SW2 Down -> CSYnch
  - Switch SW2 Up   -> HSync

![Image of RGB2VGA2-01](https://github.com/EmberHeavyIndustries/AMI-RGB2VGAULTIMATE/blob/main/Docs/RGB2VGAULTIMATE.jpg)

# SCHEMATICS

Full schematics can be found here

[RGB2VGAPLUS Schematics](https://github.com/EmberHeavyIndustries/AMI-RGB2VGAULTIMATE/blob/main/Hardware/Schematic_RGB2VGA_V3_2023-11-02.pdf)

# MAKER's FILES

[Full RGB2VGAPLUS BOM](https://github.com/EmberHeavyIndustries/AMI-RGB2VGAULTIMATE/blob/main/Hardware/BOM_PCB_RGB2VGA_V3_2023-11-02.csv) and [GERBER files](https://github.com/EmberHeavyIndustries/AMI-RGB2VGAULTIMATE/blob/main/Hardware/Gerber_PCB_RGB2VGA_V3.zip) can be freely downloaded.
Also check PIck&Place report inside the Hardware directory, if needed


## **LICENSE TERMS**
[![License: CC BY-NC-SA 4.0](https://img.shields.io/badge/License-CC%20BY--NC--SA%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc-sa/4.0/)

### **Schematics and pcb gerbers**
are open source, released under the Creative Commons CC BY-NC license.
This means that you are free to:

|                      |                                                                        |
| -------------------- | ---------------------------------------------------------------------- |
|      SHARE           |      copy and redistribute the material in any medium or format        |
|      ADAPT           |      remix, transform, and build upon the material                     |

      
Under the following terms:

|                       |                                                                        |
| --------------------- | ---------------------------------------------------------------------- |
|     Attribution       | You must give appropriate credit, provide a link to the license, and indicate if changes were made. You may do so in any reasonable manner, but not in any way that suggests the licensor endorses you or your use. |
|      NonCommercial    | You may not use the material for commercial purposes.                  |
|      ShareAlike       | If you remix, transform, or build upon the material, you must distribute your contributions under the same license as the original.          |
| No additional restrict| You may not apply legal terms or technological measures that legally restrict others from doing anything the license permits.  |



