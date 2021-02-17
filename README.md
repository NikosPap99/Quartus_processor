# Quartus_processor
 A simple processor developed with Quartus.

 This project was developed using Quartus II 9.1sp2 Web Edition and was run on the EP2C35F672C6 board. If you want to test it on another board, you have to assign the appropriate pins and change the device settings to your device.

 ## Description 

 This is a processor implementation. It has a datapath containing two 4-bit registers A, B who can load a value parallely or shift their values. Register A also has the ability to store the sum (or difference according to the ALU operation) of the two numbers (A - B, A + B).

As implied, the ALU of the datapath can make two operations: add/subtract. It has a control signal as input in order for the control unit to be able to control which operation is happening in each clock palm.

There is also a Z-flag, which is set to 1 whenever the two numbers A, B are equal.

The control unity that has been constructed works as follows: Up until it's input "Start" is set to 1, it loads a 4-bit number determined by the 4 switches input to registers B, A in turns. First, it loads the number determined by the switches to reg B, then A, then B etc. until "Start" is
set to 1. Once that happens, the control unit orders the datapath to subtract B from A. Z-flag is set to 1 if the subtraction is 0 (which means the numbers are equal). The result of this operation is loaded to register A IF the result is not 0.

The values of registers A, B will be displayed on the LCD display at any given moment.

## How to use

1. Download the files.
2. Open Processor.qpf.
3. Go to Processing > Start Compilation.
4. Connect the usb blaster to your device.
5. Go to Tools > Programmer.
6. Go to Hardware Setup and choose the usb blaster.
7. Press start.
8. Enjoy!