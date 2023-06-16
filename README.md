# ATtiny_HVSP-ISP_stripboard

## Summary

This is a multi-purpose board, for DIP-8 ATtiny ICs, designed to be used in conjunction with an Arduino Uno:
- Development board with on-board I/O (such as buttons, LEDs and potentiometer) for testing code
- Dual programming board:
  - ISP - Standard
  - HVSP - Fuse resetting  

Features include:
- ZIF socket
- Breakout connections for DigiSpark/DigiStump fuse resetting (HVSP)
- On-board 10 µF electroytic (for Arduino RESET supression)

Note that even though this board is designed with the Arduino Uno in mind, it is ***not*** an Arduino Uno "shield", due to its size - although, apart from the `5V` and `RESET` pins, it *could* (at a pinch) be fitted into the header for pins `D8` to `D13`. Note that D7 would require a "bent" header pin, due to the unorthodox layout of the Arduino Uno.

The board can also be used with other Arduino boards, so long as the pins are connected appropriately.

The 16 pin ZIF socket is *logically* split into two:

- The top half (pins 1-4 and pin 13-16) are used as an ISP and for the dev-board
- The bottom half (pins 5-8 and 9-12) are used exclusively for HVSP

## Influences

Derived from the boards of [Ralph S Bacon](https://github.com/RalphBacon), [GadgetReboot](https://github.com/GadgetReboot) and [Wayne Holder](https://github.com/wholder):

- Watch Ralph S Bacon's videos: 
  - [#87 Six, yes SIX, GPIO pins on an ATTiny85](https://www.youtube.com/watch?v=yAT_TdD6nL0), and;
  -  [#84 Making the ATTiny85 easier to program](https://www.youtube.com/watch?v=HJ4mhXv-MXo)
- Watch GadgetReboot's videos: 
  - [ATTiny85 Fuse Resetter with Arduino](https://www.youtube.com/watch?v=JskwC4bhgx4), and;
  -  [How to Program Micronucleus Bootloader on ATTiny85 and Digispark](https://www.youtube.com/watch?v=RlscDz5JCcI&list=RDCMUCwiKHTegfDe33K5wnmyULog&index=4)
- Watch Wayne Holders videos:
  - [AVR-Arduino Hardware Debugger on the Cheap](https://www.youtube.com/watch?v=kI_Z78a_0y0), and; 
  - [AVR Debugger Part 2](https://www.youtube.com/watch?v=F1202b0l5DA)

### Layout

[![ATtiny_HVSP-ISP_stripboard][1]][1]

### Schematic

[![ATtiny_HVSP-ISP_schematic][6]][6]

Various elements are taken from the different designs:
- The ZIF socket from the Bacon design(s)
- The ATtiny reset taken from the Bacon modification of the mini-shield ATtiny programmer, shown in [#84 Making the ATTiny85 easier to program](https://www.youtube.com/watch?v=HJ4mhXv-MXo) at [22:42](https://www.youtube.com/watch?v=HJ4mhXv-MXo&t=1362s) and explained at [24:43](https://www.youtube.com/watch?v=HJ4mhXv-MXo&t=1483s)
- The high side switching and use of the 12 V booster PCB from the GadgetReboot design(s)
- Use of MAX662 in place of the 12 V booster PCB from Wayne Holder (see [ATTiny10 C IDE and Improved Device Programmer](https://sites.google.com/site/wayneholder/attiny10-c-ide-and-improved-device-programmer))
- The simplified high side switching from the Holder design(s)
- Plus some other elements taken from some commerical boards:
  - The "dev-board" I/O functionality (included LEDs, buttons and trim pot for ADC), taken from these two boards:
     - [New Attiny13 AVR Developments Board Module Learning Experiment Board Develop Test Boards with USB Power Cable for Attiny 13 AVR](https://www.aliexpress.com/item/1005002801247155.html?spm=a2g0o.productlist.main.1.55c67a5eZb77Wy&algo_pvid=2a8ca812-60f9-4822-b005-fc71373366a5&algo_exp_id=2a8ca812-60f9-4822-b005-fc71373366a5-0&pdp_npi=3%40dis%21GBP%214.23%213.81%21%21%21%21%21%402100b69816848452643623796d0788%2112000022251128135%21sea%21UK%21840970582&curPageLogUid=wQBA2SYfNF9K)
     - [Attiny13 AVR Development Board Learning Board Experimental Test Boards](https://www.aliexpress.com/item/32813240677.html?spm=a2g0o.productlist.main.11.55c67a5eae9WTW&algo_pvid=2a8ca812-60f9-4822-b005-fc71373366a5&algo_exp_id=2a8ca812-60f9-4822-b005-fc71373366a5-5&pdp_npi=3%40dis%21GBP%213.36%213.36%21%21%21%21%21%402100b69816848452643623796d0788%2164617970276%21sea%21UK%21840970582&curPageLogUid=9LjSDDicM1P4)

[![Attiny13 AVR Development Board Learning Board Experimental Test Boards][11]][11]

## Variants

There are four basic variants of the board (although the size is constant) depending on whether:

1. Omron momentary button size:
   - 6x6 mm, or;
   - 12x12 mm  
2. The source of the 12 V required for the HV_RESET:
   - The MT3608 12 V w/USB booster PCB, or;
   - MAX 662 is used

The MT3608 12V w/USB booster PCB (31 x 18 mm) is available here: [MT3608 DC-DC Step Up Converter Booster Power Supply Module Boost Step-up Board MAX output 28V 2A for arduino diy kit](https://www.aliexpress.com/item/1005001622010062.html?spm=a2g0o.productlist.main.9.568ac43d7kAbTn&algo_pvid=59d1f14d-ccaf-45ca-8d25-ea006181c474&aem_p4p_detail=20230514025002602703329491940009021591&algo_exp_id=59d1f14d-ccaf-45ca-8d25-ea006181c474-4&pdp_npi=3%40dis%21GBP%210.38%210.31%21%21%21%21%21%402100bb6416840578020693389d077e%2112000016846842843%21sea%21UK%21840970582&curPageLogUid=uKbZ08D7oXeC&ad_pvid=20230514025002602703329491940009021591_1&ad_pvid=20230514025002602703329491940009021591_1)

[![MT3608 12V w/USB booster PCB][8]][8]

Notes:
- Resulting from limitations of the [DIY Layout Creator software](https://github.com/bancika/diy-layout-creator), the Omron buttons can not be *accurately* visualised/represented, so instead their general location is shown and the spacing for the placement of the button varies, depending on the size of the button used (6x6 mm => 4 holes wide, 12x12 mm => 6 holes wide).
- It is  easy to implement a single transistor high side switch, en lieu of the dual transistor configurations shown, by just omitting the NPN transistors and connecting the digital output directly to the gate of the p-channel FET. However, the logic of the switch would be inverted (from active `HIGH` to active `LOW`).
- It is possible replace the p-channel FETs with PNP transistors, if desired, with a minimal amount of rework.

See [More ATtiny](https://gr33nonline.wordpress.com/2023/05/12/more-attiny/) for further details.

These layouts are designed to fit two (commonly avaiable) stripboard sizes:
- 100 x 160 mm => 35 strips x 61 holes (2135T)
- 65 x 145 mm (2.5″ x 5.75″) => 24 strips x 56 holes

## Layout #1:  100 x 160 mm => 35 strips x 61 holes

These four layouts below fit on to a 100 x 160 mm => 35 strips x 61 holes (2135T) board. 

### Using 12 V booster PCB

#### 6x6 mm Omron with 12 V booster PCB

v1.0.4.6.2

[![ATtiny_HVSP-ISP_stripboard v1.0.4.6.2 - 6x6 mm Omron with 12 V booster PCB][2]][2]

#### 12x12 mm Omron with 12 V booster PCB

v1.0.6.1

[![ATtiny_HVSP-ISP_stripboard v1.0.6.1 - 12x12 mm Omron with 12 V booster PCB][3]][3]

### Using MAX662

#### Schematic

[![ATtiny_HVSP-ISP_schematic - with MAX662][7]][7]

#### 6x6 Omron with MAX662

v1.0.4.7.6

[![ATtiny_HVSP-ISP_stripboard v1.0.4.7.6 - 6x6 mm Omron with MAX662][4]][4]

#### 12x12 mm Omron with MAX662

v1.0.7.5

[![ATtiny_HVSP-ISP_stripboard v1.0.7.5 - 12x12 mm Omron with MAX662][5]][5]


Notes:

- The 12x12 mm layouts can also be used with the 6x6 mm buttons, which would allow for 100 nF to 1 µF capacitors to be used in parallel to the buttons, for debouncing reasons.
- If the older MAX662 is used en lieu of the later MAX662A and MAX662A+, then an additional ceramic 100 nF (C9) is required across pins 5 and 6. Note: C9 can be omitted if the newer MAX662A(+) is used, but no harm is done by leaving it there, either.

## Layout #2: 65 x 145 mm => 24 strips x 56 holes

This is a (horizontally) compressed version of the layout. As a result of the compression, some features available in the larger board have been either removed, or changed:

- There is no longer a set of header pins (that replicate the lower side of the Arduino Uno) along the left hand side
- The connection to the Arduino RESET pin has been moved
- The additional (and redundant) set of sockets either side of the ZIF socket have been removed.
- The location of the HVSP breakout sockets (for DigiSpark/DigiStump fuse resetting) has been changed - these connections are shown as red
- The space for adding optional capacitors for debouncing SW1 and SW2 has been removed

Note: The larger size of the 12x12 mm Omron buttons makes it rather difficult to fit a layout using them, on to a 65 x 145 mm stripboard. Hence, the  *compressed* layouts for 12x12 mm Omron buttons are significantly different layouts.

### Using 12 V booster PCB
#### 6x6 mm Omron with 12 V booster PCB

v1.0.4.6.6

[![ATtiny_HVSP-ISP_stripboard v1.0.4.6.6 - 6x6 mm Omron with 12 V booster PCB][9]][9]

#### 12x12 mm Omron with 12 V booster PCB

v1.0.6.5

[![ATtiny_HVSP-ISP_stripboard v1.0.6.5 - 12x12 mm Omron with 12 V booster PCB][12]][12]

### Using MAX662

#### 6x6 Omron with MAX662

v1.0.4.7.6

[![ATtiny_HVSP-ISP_stripboard v1.0.4.7.13 - 6x6 mm Omron with MAX662][10]][10]

#### 12x12 mm Omron with MAX662

1.0.7.8.1

[![ATtiny_HVSP-ISP_stripboard v1.0.7.8.1 - 12x12 mm Omron with MAX662][13]][13]

## Layout #3: 65 x 145 mm => 24 strips x 61 holes

#### 12x12 mm Omron with MAX662

1.0.7.6

***Image!!!!***



  [1]: https://github.com/greenonline/ATtiny_HVSP-ISP_stripboard/blob/main/DIYLC_files/Dual_ISP_HVSP_ATtiny_symmetry_shorter_v0.0.png "ATtiny_HVSP-ISP_stripboard"
  [2]: https://github.com/greenonline/ATtiny_HVSP-ISP_stripboard/blob/main/DIYLC_files/Dual_HVSP_ATtiny_v1.0.4.6.2.png  "ATtiny_HVSP-ISP_stripboard v1.0.4.6.2 - 6x6 mm Omron with 12 V booster PCB"
  [3]: https://github.com/greenonline/ATtiny_HVSP-ISP_stripboard/blob/main/DIYLC_files/Dual_HVSP_ATtiny_v1.0.6.1.png  "ATtiny_HVSP-ISP_stripboard v1.0.6.1 - 6x6 mm Omron with 12 V booster PCB"
  [6]: https://github.com/greenonline/ATtiny_HVSP-ISP_stripboard/blob/main/KiCAD_files/ATtiny_Dual_HVSP_ISP_Programmer/ATtiny_Dual_HVSP_ISP_Programmer.png "ATtiny_HVSP-ISP_schematic"
  [4]: https://github.com/greenonline/ATtiny_HVSP-ISP_stripboard/blob/main/DIYLC_files/Dual_HVSP_ATtiny_v1.0.4.7.6.png "ATtiny_HVSP-ISP_stripboard v1.0.4.7.6 - 6x6 mm Omron with MAX662"
  [5]: https://github.com/greenonline/ATtiny_HVSP-ISP_stripboard/blob/main/DIYLC_files/Dual_HVSP_ATtiny_v1.0.7.5.png "ATtiny_HVSP-ISP_stripboard v1.0.7.5 - 12x12 mm Omron with MAX662"
  [7]: https://github.com/greenonline/ATtiny_HVSP-ISP_stripboard/blob/main/KiCAD_files/ATtiny_Dual_HVSP_ISP_Programmer_with_MAX662A(+)/ATtiny_Dual_HVSP_ISP_Programmer_with_MAX662.png "ATtiny_HVSP-ISP_schematic - with MAX662"
  [8]: https://gr33nonline3.files.wordpress.com/2023/02/mt3608-dc-dc-step-up-converter-booster.png "MT3608 12V w/USB booster PCB"
  [9]: https://github.com/greenonline/ATtiny_HVSP-ISP_stripboard/blob/main/DIYLC_files/Dual_HVSP_ATtiny_v1.0.4.6.6.png  "ATtiny_HVSP-ISP_stripboard v1.0.4.6.6 - 6x6 mm Omron with 12 V booster PCB"
  [10]: https://github.com/greenonline/ATtiny_HVSP-ISP_stripboard/blob/main/DIYLC_files/Dual_HVSP_ATtiny_v1.0.4.7.13.png "ATtiny_HVSP-ISP_stripboard v1.0.4.7.13 - 6x6 mm Omron with MAX662"
  [11]: https://gr33nonline3.files.wordpress.com/2023/02/attiny-dev-board.png "Attiny13 AVR Development Board Learning Board Experimental Test Boards"
  [12]: https://github.com/greenonline/ATtiny_HVSP-ISP_stripboard/blob/main/DIYLC_files/Dual_HVSP_ATtiny_v1.0.6.5.png  "ATtiny_HVSP-ISP_stripboard v1.0.6.5 - 6x6 mm Omron with 12 V booster PCB"
  [13]: https://github.com/greenonline/ATtiny_HVSP-ISP_stripboard/blob/main/DIYLC_files/Dual_HVSP_ATtiny_v1.0.7.8.1.png "ATtiny_HVSP-ISP_stripboard v1.0.7.8.1 - 12x12 mm Omron with MAX662"
