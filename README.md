# Wake-on-Lan

# Program To Remotely Power On A PC Over The Internet Using The Wake-On-LAN Protocol


Wake-on-LAN (WoL) is an Ethernet or token ring computer networking standard that allows a computer to be turned on or awakened by a network message.

* The message is usually sent to the target computer by a program executed on a device connected to the same local area network, such as a smartphone.

* It is also possible to initiate the message from another network by using subnet directed broadcasts or a WOL gateway service.

* Equivalent terms include wake on WAN, remote wake-up, power on by LAN, power up by LAN, resume by LAN, resume on LAN and wake up on LAN.
# Principle of operation

* Wake-on-LAN (“WOL”) is implemented using a specially designed packet called a magic packet, which is sent to all computers in a network, among them the computer to be awakened.

* The magic packet contains the MAC address of the destination computer, an identifying number built into each network interface card (“NIC”) or other ethernet device in a computer, that enables it to be uniquely recognized and addressed on a network.

* Powered-down or turned off computers capable of Wake-on-LAN will contain network devices able to “listen” to incoming packets in low-power mode while the system is powered down.

* If a magic packet is received that is directed to the device’s MAC address, the NIC signals the computer’s power supply or motherboard to initiate system wake-up, much in the same way as pressing the power button would do.

* The magic packet is sent on the data link layer (layer 2 in the OSI model) and when sent, is broadcast to all attached devices on a given network, using the network broadcast address; the IP-address (layer 3 in the OSI model) is not used.

In order for Wake-on-LAN to work, parts of the network interface need to stay on. This consumes a small amount of standby power, much less than normal operating power. Disabling wake-on-LAN when not needed, can therefore very slightly reduce power consumption on computers that are switched off but still plugged into a power socket.

# Magic Packet Structure
The magic packet is a broadcast frame containing anywhere within its payload 6 bytes of all 255 (FF FF FF FF FF FF in hexadecimal), followed by sixteen repetitions of the target computer’s 48-bit MAC address, for a total of 102 bytes.
Since the magic packet is only scanned for the string above, and not actually parsed by a full protocol stack, it may be sent as any network- and transport-layer protocol, although it is typically sent as a UDP datagram to port 0, 7 or 9, or directly over Ethernet as EtherType 0x0842.

A standard magic packet has the following basic limitations:

1 - Requires destination computer MAC address (also may require a SecureOn password).

2 - Does not provide a delivery confirmation.

3 - May not work outside of the local network.

4 - Requires hardware support of Wake-On-LAN on destination computer.

5 - Most 802.11 wireless interfaces do not maintain a link in low power states and cannot receive a magic packet.

The Wake-on-LAN implementation is designed to be very simple and to be quickly processed by the circuitry present on the network interface card with minimal power requirement. Because Wake-on-LAN operates below the IP protocol layer the MAC address is required and makes IP addresses and DNS names meaningless.
