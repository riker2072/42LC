# 42LC
42LC calculator (alpha version)

Note for 3/4/24 update:  Added INPUT command.  When done entering the number, use ENTER (instead of R/S).  The following program codes are used (when stored in file) :
62xx for INPUT var,
63xx for INPUT reg,
66xx for INPUT ind var,
67xx for INPUT ind reg

Notes for 2/26/24 update:  Programs loaded on startup or from LOAD command have a re-scan of local labels.  This is necessary because if a program is run before the re-scan is done, it will not work.  Upon entry in program edit mode, and subsequent exit, an automatic re-scan is done.  This fix eliminates the need to enter and exit program edit mode.

Remember to use a high speed micro SD card for best results when saving data.

See the 42LCmoreNotes file for how data is saved.  Also 42LCtestPrograms for Hitomezashi and Nqueens test programs

Files test42a05.txt, test42b05.txt, test42c05.txt, test42d05.txt and test42e05.txt will contain the Hitomezashi and Nqueens test programs.  Remember to Load state 05 (see Config menu, below).

For Nqueens, XEQ OO (two letter O's).  Results stored in reg 01 to 04 (for size 4).
For Hitomezashi, you must rescan local labels:  in normal mode, do GTO HT, then enter PRGM mode, and exit PRGM mode (by exiting program mode, local labels are rescanned for the current program).  Remember to store size (<9) in S.

The Config menu (press Shift (kbp) key.  Note, currently, must enter number first, then enter Config menu.

To save a calculator state, enter a number from 1 to 99 on the stack, and press Enter.  Then press the "save" softkey.
To load a calculator state, enter a number from 1 to 99 on the stack and press Enter.  Then the "load" softkey.
If you want to change the "matrix number" variable, put the number (0 to 9) on the stack and press Enter.  Then the "mtnum" softkey.  The next new matrix will have that number.  After 9, mtnum will wrap around back to 0 and may overwrite another matrix if it was stored there.
If you want to change the program count number (useful when doing GTO ..), put the number from 0 to 14 on the stack and press Enter.  Then the "pcount" softkey.

Using GTO .####

It is possible to go to a particular program by doing a GTO .####, where #### is a 4 digit number for the address.  To go to address 99, put GTO .0099  
Entering a number more than 1499 may lead to unpredictable results.
First program is usually 0000 to 0099, second program is usually 0100 to 0199 and so on.

Burning firmware:

This 42LC firmware may be used for non-commercial personal or educational purposes. No warranties are made on the use of the firmware. It is up to the user to verify the accuracy or precision of this calculator implementation.

Go to Github riker2072 42LC repository.
Get 42LC.ino.bin, 42LC.ino.bootloader.bin and 42LC.ino.partitions.bin files.
Get Windows ESP32 flash download tool at: https://www.espressif.com/en/support/download/other-tools
Click on … to select 42LC.ino.bin file directory location. In the @ box, put 0x10000 Click on … to select 42LC.ino.bootloader.bin file directory location. In the @ box, put 0x0000 Click on … to select 42LC.ino.partitions.bin file directory location. In the @ box, put 0x8000
SPI speed is 40MHz, SPI mode is DIO. Check mark in the box labeled “DoNotChgBin”. My port settings are COM4, baud 115200. Connect the M5 Cardputer to your PC using a USB C cable. Click on START to burn the firmware.

