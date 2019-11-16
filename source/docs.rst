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

Badge communication
=============================


Scanning
-----------------------------
The badge will switch between server and client mode.
When in server mode the badge will advertise. and when in client mode the badge
will be listening for other badges.



Communication
----------------------------
communication will be over a BLE spp.


Comms notes
----------------------------
::
at+bleinit?      to get mode.
at+bleinit=2     server mode. can advertise
at+bleinit=1     client mode. can scan for advertisments
you need to set mode to 0 of you want to switch from server to client and vice versa

scanning.
at+blescan=1,1  first arg turns on continuous scanning
		omit the 2nd arg and it will scan continuously
		the second arg is how many seconds to scan for before stopping

scan messages
+BLESCAN:5f:a5:21:e5:5e:e4,-85,02011a020a0c0bff4c001006131ee4c60f3b,,1

the response, address - rssi - adv data - scan rsp data - addr type


advertising.

at+bleadvstart

module comes up in anther modules scan like this.
+BLESCAN:84:0d:8e:37:ae:5a,-67,,,0

