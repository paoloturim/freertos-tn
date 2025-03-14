Overview
========
The freertos_ecspi_loopback demo shows how the ecspi do a loopback transfer internally in FreeRTOS.
The ECSPI connects the transmitter and receiver sections internally, and the data shifted out from the 
most-significant bit of the shift register is looped back into the least-significant bit of the Shift register. 
In this way, a self-test of the complete transmit/receive path can be made. The output pins are not affected, 
and the input pins are ignored.

Toolchain supported
===================
- IAR embedded Workbench 8.30.2
- GCC ARM Embedded 7-2017-q4-major

Hardware requirements
=====================
- Micro USB cable
- FLEX-IMX8MM  board
- J-Link Debug Probe
- 12V power supply
- Personal Computer

Board settings
==============
No special settings are required.


Prepare the Demo
================
1.  Connect 12V power supply and J-Link Debug Probe to the board, switch SW101 to power on the board
2.  Connect a USB cable between the host PC and the J901 USB port on the target board.
3.  Open a serial terminal with the following settings:
    - 115200 baud rate
    - 8 data bits
    - No parity
    - One stop bit
    - No flow control
4.  Download the program to the target board.
5.  Either press the reset button on your board or launch the debugger in your IDE to begin running the demo.

Running the demo
================
If the demo run successfully, the below log will be print in the terminal window:
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
***FreeRTOS ECSPI Loopback Demo***

This demo is a loopback transfer test for ECSPI.
The ECSPI will connect the transmitter and receiver sections internally.
So, there is no need to connect the MOSI and MISO pins.

FreeRTOS ECSPI loopback test pass!
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Customization options
=====================

