# Radio-86RK SRAM firmware

radio86rk-monitor.bin - Monitor (28C64)
radio86rk-font.bin    - Font    (28C16)

## PS/2 Keyboard Adapter for Radio-86RK and similar computers with ATMega48(/88/168)

orion_kb_m48.hex - for ATmega48/88
orion_kb_m168.hex - for ATmega168/328

### PS/2 Keyboard Layouts

PS/2 adapter firmware implements two alternative keyboard layouts for convenience when working with both Latin and Cyrillic, which use different layouts on RK86 from compared to PC. With two layouts, you will see on the screen what is on the key.

Scroll Lock key will switch between two layouts. Scroll Lock indicator will show what layout is active. What Scroll Lock is off, the layout is Latin (QWERTY), when on - Cyrillic.

### Radio-86RK matrix layout

    | D7 | D6 | D5 | D4 | D3 | D2 | D1 | D0
 --- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---
 A7 | SP | ^  | ]  | \  | [  | Z  | Y  | X
 A6 | W  | V  | U  | T  | S  | R  | Q  | P
 A5 | O  | N  | M  | L  | K  | J  | I  | H
 A4 | G  | F  | E  | D  | C  | B  | A  | @
 A3 | /  | .  | =  | ,  | ;  | :  | 9  | 8
 A2 | 7  | 6  | 5  | 4  | 3  | 2  | 1  | 0
 A1 | v  | -> |  ^ | <- | BS | CR | LF | TAB
 A0 | F5 | F4 | F3 | F2 | F1 | ESC | CLR | ^\

### Programming ATMega48 with PS/2 adapter firmware

The default Fuse and Lock bits for an ATmega48 are as follows:

Lock(&Fuse) | Fuse(Low)  | Fuse(High)    | Fuse(Ext)
------------ | ------------ | --------------- | ------------------
[v] LB1     | [ ] CKSEL0 | [v] BODLEVEL0 | [v] SELFPRGEN
[v] LB2     | [v] CKSEL1 | [v] BODLEVEL1 | [v] -
[v] BLB01   | [ ] CKSEL2 | [v] BODLEVEL2 | [v] -
[v] BLB10   | [ ] CKSEL3 | [v] EESAVE    | [v] -
[v] BLB11   | [ ] SUT0   | [v] WDTON     | [v] -
[v] BLB12   | [v] SUT1   | [ ] SPIEN     | [v] -
[v] -       | [v] CKOUT  | [v] DWEN      | [v] -
[v] -       | [ ] CKDIV8 | [v] RSTDISBL  | [v] -

You need to change:
1) Fuse(Low)/CKDIV8
2) Fuse(High)/BODLEVEL0,1

The result should look like:

Lock(&Fuse) | Fuse(Low)  | Fuse(High)    | Fuse(Ext)
------------ | ------------ | --------------- | ------------------
[v] LB1     | [ ] CKSEL0 | [ ] BODLEVEL0 | [v] SELFPRGEN
[v] LB2     | [v] CKSEL1 | [ ] BODLEVEL1 | [v] -
[v] BLB01   | [ ] CKSEL2 | [v] BODLEVEL2 | [v] -
[v] BLB10   | [ ] CKSEL3 | [v] EESAVE    | [v] -
[v] BLB11   | [ ] SUT0   | [v] WDTON     | [v] -
[v] BLB12   | [v] SUT1   | [ ] SPIEN     | [v] -
[v] -       | [v] CKOUT  | [v] DWEN      | [v] -
[v] -       | [V] CKDIV8 | [v] RSTDISBL  | [v] -
