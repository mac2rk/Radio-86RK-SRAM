# Radio-86RK SRAM Memory Map
* 0000h - 7FFFh - SRAM
  * 7600h - 7FFFh - Display buffer and monitor variables
* 8000h - 8FFFh - 8255A PPI (D20 - Keyboard and Cassette Tape Recorder)
  * 8000h - Channel A data
  * 8001h - Channel B data
  * 8002h - Channel C data
  * 8003h - Control word
* 9000h - 9FFFh - Unused
* 0A000h - 0AFFFh - 8255A PPI (D14 - Expansion Port)
  * 0A000h - Channel A data
  * 0A001h - Channel B data
  * 0A002h - Channel C data
  * 0A003h - Control word
* 0B000h - 0BFFFh - Unused
* 0C000h - 0CFFFh - 8275 CRT Controller
* 0D000h - 0DFFFh - Unused
* 0E000h - 0EFFFh - 8257 DMA Controller (write only)
* 0E000h - 0FFFFh - Monitor ROM (read only)
