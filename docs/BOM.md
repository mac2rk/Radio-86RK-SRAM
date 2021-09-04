# Radio-86RK SRAM Bill of Materials

Name    | Type      | Quantity  | Notes
------- | --------- | --------- | ------
D1      | i8224     | 1         | eBay
D2      | i8257     | 1         | eBay 	
D3      | 74LS92N   | 1 	    | 
D4      | 74LS08N   | 1 	    |
D5      | 74LS86N   | 1 	    |
D6      | i8080     | 1 	    | eBay
D7      | i8212     | 1         | eBay
D8      | i8275     | 1         | eBay
D9      | 74LS04N   | 1         | 	 
D10     | 74LS00N   | 1         | 	 
D11     | 74LS138N  | 1         | 	 
D12     | AT28C16   | 1         | 	 
D13     | 74S74N    | 1 	    | 
D14, D20| i8255(A)  | 2         | eBay	 
D15     | 74198N    | 1 	    | eBay
D17     | AT28C64   | 1         | eBay
D21, D32| LT1006    | 2         |
D22     | BS62LV256, UT62256CPC, etc. | 1 | 	 
D30     | ATMega48/88/168/328 | 1 | 	 
D31     | AT28C256  | 1         | 	 
D33     | XP POWER IW2405SA | 1 | or similar
D34     | XP POWER JTF1024S05 | 1 | or similar
D35     | XP POWER JTF1024S12 | 1 | or similar
n/a | Socket DIL08 300mil | 2 | optional by recommended
n/a | Socket DIL14 300mil | 6 | optional by recommended
n/a | Socket DIL16 300mil | 2 | optional by recommended
n/a | Socket DIL24 600mil | 3 | optional by recommended
n/a | Socket DIL28 300mil | 1 | optional by recommended
n/a | Socket DIL28 600mil | 3 | optional by recommended
n/a | Socket DIL40 600mil | 5 | optional by recommended
P14, P20| 2.54mm 2x13 box header, right angle | 2 | 	 
TAPE_IN,TAPE_OUT,VIDEO_OUT | LUMBERG WBTOR RCA connector | 2 | obsolete
DIN1    | Mini-DIN 6-way    | 1 |
EXT_RST | 2.54mm 1x2 header | 1 | 	 
ISP     | 2.54mm 2x3 header | 1 | 	 
24V_IN  | 5.5mm x 2.1мм or 5.5mm x 2.5mm barrel power connector | 1 | 	 
R1  | Resistor 2kOhm 1/4W | 1 | 	 
R3, R15, R17, R32, R33 | Resistor 1kOhm 1/4W |	5 | 	 
R4, R5, R104 | Resistor array 5x4.7kOhm | 3 | bus topology	 
R6-R12  | Resistor array 7x10kOhm |	1 | bus topology
R16     | Resistor 680Ohm 1/4W | 1 |
R18     | Resistor 51Ohm 1/4W | 1 | 	 
R19     | Resistor 150Ohm  1/4W | 1 | 	 
R29     | Resistor 12kOhm 1/4W | 1 | 	 
R30     | Resistor 2.4kOhm 1/4W | 1 | 	 
R31, R101, R103, R110, R111 | Resistor 330Ohm 1/4W | 6 | 	 
R109    | Resistor 1.1kOhm 1/4W | 1 |  	  	 
R107, R108 | Resistor 10kOhm 1/4W | 2 | 	 
C2 	    | Capacitor ceramic 0.47uF LS=5mm |	1 | 	 
C3 	    | Capacitor electrolytic 22..47uF LS=2.5mm | 1 | 	 
C4 	    | Capacitor ceramic 22nF LS=5mm | 1 | 	 
C5 	    | Capacitor ceramic 0.22uF LS=5mm | 1 | 	 
C6 	    | Capacitor ceramic 2.2nF LS=5mm  | 1 |  	 
C7-C12, C17-C25, C101-C114 | Capacitor ceramic 0.1uF LS=5mm | 29 | 	 
C115(116) |	Capacitor electrolytic 330..1000uF LS=5 or 7.5mm | 1 | 	 
VD1, VD3, VD101 | 1N4148 | 3 | 	 
VT2     | 2N3904 | 1 | 	 
+5V, +12V, -5V, LED | LEDs 3mm | 4 | 	 
TVS1    | TVS 24V | 1 | 	 
F1      | PTC fuse 0.5A LS=5mm  | 1 | 	 
H1      | Piezo speaker LS=10mm | 1 | 	 
Z1      | Crystal 18.432МГц, HC-49 | 1 | 	 
PIXEL_CLK |	Oscillator TTL/HCMOS 16МГц, DIL8 | 1 | 	 
RESET   | TACT momentary button | 1 | 	 

Comments:
* Logic can be TTL (e.g. 74198N) or from LS/ALS/HCT familes
* Opamp (D21) can be any single opamp rated for +/-5V operation
* Opamp (D32) can be any single opamp rated for 12..24V single supply operation
* For D30, any of ATmega48/88/168/328 can be used можно использовать, but not that 48/88 have different firmware from 168/328
* DC/DC moduled can be replaced with equivalents, provided that the @Enable@ pin is connected correctly.
* Resistor arrays can be anything with bus topology (e.g. one commpon pin) with the value between 4..20kOhm.Bourns 4308R-101 and 4306R-101 are sutbale examples. 
* R109's value on the schetic and silk screen is wrong - it should be 1 to 1.5kOhm.
* LUMBERG WBTOR RCA connectors are obsolete and no longer manufactured. Consider using offboard connectors or amending the board design for the connectors that are available.
