# Network Devices

<br/>

## Common Devices

**Router**
- Connects different networks together.
- Directs data packets to their destination.
- Commonly used to connect a local network to the Internet.

**Switch**
- Connects multiple devices within a local area network (LAN).
- Sends data only to the intended device, improving efficiency.

**Hub**
- Connects multiple devices in a network.
- Broadcasts data to all connected devices.
- Less efficient than a switch.

**Modem**
- Converts digital signals to analog signals and vice versa.
- Enables Internet access through an Internet Service Provider (ISP).

**Access Point (AP)**
- Provides wireless connectivity to devices.
- Extends the coverage of a Wi-Fi network.

**Network Interface Card (NIC)**
- Allows a device to connect to a network.
- Can be wired (Ethernet) or wireless (Wi-Fi).

**Repeater**
- Strengthens and regenerates weak signals.
- Extends the range of a network.

**Bridge**
- Connects two network segments.
- Reduces unnecessary network traffic.

<br/>

## Network Devices and Their OSI Layers

| Network Device                   | OSI Layer                                                   | Function                                                                              |
| -------------------------------- | ----------------------------------------------------------- | ------------------------------------------------------------------------------------- |
| **Hub**                          | **Layer 1 – Physical Layer**                                | Broadcasts data to all connected devices without examining the data.                  |
| **Repeater**                     | **Layer 1 – Physical Layer**                                | Regenerates and strengthens weak signals to extend network distance.                  |
| **Modem**                        | **Layer 1 – Physical Layer**                                | Converts digital signals to analog signals and vice versa for Internet communication. |
| **Network Interface Card (NIC)** | **Layer 2 – Data Link Layer** (also interacts with Layer 1) | Provides a device with network connectivity and a unique MAC address.                 |
| **Bridge**                       | **Layer 2 – Data Link Layer**                               | Connects network segments and filters traffic based on MAC addresses.                 |
| **Switch**                       | **Layer 2 – Data Link Layer**                               | Forwards frames to the correct device using MAC addresses.                            |
| **Wireless Access Point (AP)**   | **Layer 2 – Data Link Layer**                               | Connects wireless devices to a wired network.                                         |
| **Router**                       | **Layer 3 – Network Layer**                                 | Routes packets between different networks using IP addresses.                         |
| **Layer 3 Switch**               | **Layer 3 – Network Layer**                                 | Combines switching and routing functions within a network.                            |
| **Gateway**                      | **Layers 4–7 (Transport to Application)**                   | Translates data between different protocols or network architectures.                 |
| **Firewall**                     | **Layers 3, 4, and 7**                                      | Filters and controls network traffic based on security rules.                         |
