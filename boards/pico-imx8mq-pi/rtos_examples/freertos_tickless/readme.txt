Overview
========
This document explains the freertos_tickless example. It shows the CPU enter at sleep mode and then
it is waked up by expired time delay that using GPT module.

Hardware requirements
=====================
- Micro USB cable
- PICO-IMX8MQ  board
- J-Link Debug Probe
- 12V power supply
- Personal Computer

Board settings
==============
No special settings are required.



Prepare the Demo
================
1.  Connect 12V power supply and J-Link Debug Probe to the board, switch SW701 to power on the board
2.  Connect a USB cable between the host PC and the J1701 USB port on the target board.
3.  Open a serial terminal with the following settings:
    - 115200 baud rate
    - 8 data bits
    - No parity
    - One stop bit
    - No flow control
4.  Download the program to the target board.
5.  Launch the debugger in your IDE to begin running the demo.

Running the demo
================
After the board is flashed the Tera Term will start periodically printing number tick count when the CPU
is running.

When the CPU is running and get tick count number, press button on board that suggest message display on
console screen ("eg:Press SW3 <or SW1,SW2> to wake up the CPU") to wake up CPU then Tera Term
will printing “CPU waked up by EXT interrupt” message.

Example output:

Press any key to start the example
Tickless Demo example
Press or turn on SWx to wake up the CPU

Tick count :
1
5001
10001
CPU waked up by EXT interrupt
15001
20001
25001

Explanation of the example
The example application will get tick count number after every period time delay vTaskDelay(time)
When this function called the CPU enter to sleep mode a period of time that called by vTaskDelay
function.

While the CPU is sleeping, if several time on board then CPU waked up
by external interrupt and continuous enter sleep mode after complete interrupt service.
The period of time delay is not change after occur external interrupt.

Toolchain supported
===================
- IAR embedded Workbench  8.32.1
- GCC ARM Embedded  7.3.1

