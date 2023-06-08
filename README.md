# ATtiny_HVSP-ISP_stripboard

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

[![ATtiny_HVSP-ISP_stripboard][1]][1]

[![ATtiny_HVSP-ISP_schematic][2]][2]

  [1]: https://github.com/greenonline/ATtiny_HVSP-ISP_stripboard/blob/main/DIYLC_files/Dual_ISP_HVSP_ATtiny_symmetry_shorter_v0.0.png "ATtiny_HVSP-ISP_stripboard"
  [2]: https://github.com/greenonline/ATtiny_HVSP-ISP_stripboard/blob/main/KiCAD_files/ATtiny_Dual_HVSP_ISP_Programmer/ATtiny_Dual_HVSP_ISP_Programmer.png "ATtiny_HVSP-ISP_schematic"

Various elements are taken from the different designs:
- The ZIF socket from the Bacon design(s)
- The ATtiny reset taken from the Bacon modification of the mini-shield ATtiny programmer, shown in [#84 Making the ATTiny85 easier to program](https://www.youtube.com/watch?v=HJ4mhXv-MXo) at [22:42](https://www.youtube.com/watch?v=HJ4mhXv-MXo&t=1362s) and explained at [24:43](https://www.youtube.com/watch?v=HJ4mhXv-MXo&t=1483s)
- The high side switching and use of the 12 V booster PCB from the GadgetReboot design(s)
- Use of MAX662 in place of the 12 V booster PCB from Wayne Holder (see [ATTiny10 C IDE and Improved Device Programmer](https://sites.google.com/site/wayneholder/attiny10-c-ide-and-improved-device-programmer))
- The simplified high side switching from the Holder design(s)
- Plus some other elements taken from some commerical boards:
  - The "dev-board" I/O functionality (included LEDs and buttons and trim pot for ADC), taken from these two boards:
     - [New Attiny13 AVR Developments Board Module Learning Experiment Board Develop Test Boards with USB Power Cable for Attiny 13 AVR](https://www.aliexpress.com/item/1005002801247155.html?spm=a2g0o.productlist.main.1.55c67a5eZb77Wy&algo_pvid=2a8ca812-60f9-4822-b005-fc71373366a5&algo_exp_id=2a8ca812-60f9-4822-b005-fc71373366a5-0&pdp_npi=3%40dis%21GBP%214.23%213.81%21%21%21%21%21%402100b69816848452643623796d0788%2112000022251128135%21sea%21UK%21840970582&curPageLogUid=wQBA2SYfNF9K)
     - [Attiny13 AVR Development Board Learning Board Experimental Test Boards](https://www.aliexpress.com/item/32813240677.html?spm=a2g0o.productlist.main.11.55c67a5eae9WTW&algo_pvid=2a8ca812-60f9-4822-b005-fc71373366a5&algo_exp_id=2a8ca812-60f9-4822-b005-fc71373366a5-5&pdp_npi=3%40dis%21GBP%213.36%213.36%21%21%21%21%21%402100b69816848452643623796d0788%2164617970276%21sea%21UK%21840970582&curPageLogUid=9LjSDDicM1P4)

There are four basic variants of the board (although the size is constant) depending on whether:

1. 6x6 mm or 12x12 mm Omron momentary buttons are used 
2. The 12 V w/USB booster PCB or the MAX 662 is used

Notes:
- Resulting from limitations of the [DIY Layout Creator software](https://github.com/bancika/diy-layout-creator), the Omron buttons can not be *accurately* visualised/represented, so instead their general location is shown and the spacing for the placement of the button varies, depending on the size of the button used (6x6 mm => 4 holes wide, 12x12 mm => 6 holes wide).
- It is  easy to implement a single transistor high side switch, en lieu of the dual transistor configurations shown, by just omitting the NPN transistors and connecting the digital output directly to the gate of the p-channel FET. 
- It is possible replace the p-channel FETs with PNP transistors, if desired, with a minimal amount of rework.

See [More ATtiny](https://gr33nonline.wordpress.com/2023/05/12/more-attiny/) for further details.

#### 6x6 mm Omron with 12 V booster PCB
Coming soon!
#### 12x12 mm Omron with 12 V booster PCB
Coming soon!
#### 6x6 Omron with MAX662
Coming soon!
#### 12x12 mm Omron with MAX662
Coming soon!
