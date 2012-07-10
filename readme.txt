This is a mixture of USBaspLoader (http://www.obdev.at/products/vusb/usbasploader.html) and LUFA (http://www.fourwalledcubicle.com/LUFA.php)

The goal is to make a bootloader for the USB capable AVR microcontrollers, but:

 * using low speed USB instead of full speed
   * this is a requirement because the internal RC oscillator of the U4 series is only accurate enough for low speed USB devices, not full speed USB
 * compatible with AVRDUDE

== Version 2012-07-10-18:30 ==

 * Discovered that a 4048 byte file wouldn't verify properly, the writing works but reading had a tiny bug
 * Fixed the above bug

== Version 2012-07-10-00:02 ==

 * Fixed AVRDUDE errors

== Version 2012-07-09-22:50 ==
 
 * Put on GitHub for the first time, my first time putting something on GitHub
 * Works with AVRDUDE, able to write and verify 3376 bytes on an ATmega32U4, and the code behaved as expected
 * AVRDUDE will show "avrdude: error: usbasp_transmit: usb_control_msg: sending control message failed, win error: A device attached to the system is not functioning." all the time but the code does actually work
 * Compiles to about 2798 bytes, requires a 4K of bootloader space
 * The original LUFA makefile requires some modifications to work on my computer
 * Currently, only the signature bytes of the ATmega32U4 is implemented
 
 * Please help me fix the errors and make the code friendly for all USB capable AVR microcontrollers
 