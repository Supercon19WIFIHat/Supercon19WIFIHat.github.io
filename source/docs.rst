Problems with module
=========================
Sadly, this module draws too much power from the badge and causes a reset.
It might be usefull as a PMOD on other projects.

If you want a 3rd UART out the PMOD connector then take a look at the fpgasoc repo for an example of how to do this.


Flashing your badge
=========================
You need to flash your badge with a modified SOC image.
This image adds a 3rd UART and routes it to the PMOD connector.

Download the following file and Run the following command to flash your badge.

Talking to the module UART
================================
The UART can be found at base address 0x10000020


Module AT command set
=============================
Go here https://github.com/Supercon19WIFIHat/esp-at/blob/master/docs/ESP_AT_Commands_Set.md to see a list of commands the module supports.


