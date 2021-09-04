# Radio-86RK SRAM Monitor
(based on @skiselev's work)

## Monitor Commands
* **D\<Start_Address\>,\<End_Address\>** - Display memory content in hexadecimal
* **L\<Start_Address\>,\<End_Address\>** - Display memory content in ASCII
* **F\<Start_Address\>,\<End_Address\>,\<Value\>** - Fill memory with the specified value
* **M\<Address\>** - Modify memory content
* **T\<Start_Address\>,\<End_Address\>,\<Destination_Start_Address\>** - Copy memory block to destination
* **C\<Start_Address\>,\<End_Address\>,\<Destination_Start_Address\>** - Compare memory block with destination
* **S\<Start_Address\>,\<End_Address\>,\<Value\>** - Search memory for a value
* **R\<ROM_Start_Address\>,\<ROM_End_Address\>,\<Destination_Start_Address\>** - Read from the ROM cartridge
* **G\<Start_Address\>\[,End_Address\]** - Run code, optionally stop at the specified address
* **X** - Display and modify registers
* **O\<Start_Address\>,\<End_Address\>\[,Speed\]** - Write memory to cassette. Default speed is 1Dh / 1200 bps
* **I\[Offset\]\[,Speed\]** - Read data from to cassette memory at specified offset

## Monitor Subroutines:
* 0F803h - Keyboard input
  * Input: None
  * Output: A - character code read from keyboard
* 0F806h - Cassette input
  * Input: A=0FFh - with sync; A=08h - no sync
  * Output: A - data read from cassette
* 0F809h - Print character to screen
  * Input: C - character to print
* 0F80Ch - Cassette output
  * Input: C - data to write
* 0F812h - Query keyboard
  * Output: A=00h - key not pressed; A=0FFh - key pressed
* 0F815h - Print to screen in hex
  * Input: A - data to print
* 0F818h - Print string
  * Input: HL - string address
* 0F81Bh - Get key
  * Output: A=0FFh - key not pressed; A=0FEh - Rus/Lat; otherwise A - key code
* 0F81Eh - Get cursor position
  * Output: H - row, L - column
* 0F821h - Read character from screen at current cursor position
  * Output: A - char read from screen
* 0F824h - Read from cassette
  * Input: HL - offset of memory buffer to store data to
  * Output: HL - start; DE - end; BC - checksum
