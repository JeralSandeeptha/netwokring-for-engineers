# ARP / RARP

An `ARP Request` is a network message sent to find a device's physical hardware address (MAC address) using its known IP address.

Conversely, the `RARP Request` does the exact opposite: it allows a device that only knows its physical MAC address to request its assigned IP address from a server

<br/>

## ARP (Address Resolution Protocol)

Computers use ARP to map `logical IP addresses` to `physical MAC addresses` so they can communicate across a local network.

**The Problem**:

- You know the destination device's IP address, but data links require the hardware MAC address to reach the correct Network Interface Card (NIC).

**How It Works**:

- The source device checks its local cache. If the mapping isn't there, it broadcasts an ARP Request to all devices on the network: "Who has this IP address? Please tell me your MAC address."

- The device with that specific IP address replies with an ARP Reply, stating its MAC address.

- The source device updates its ARP cache table with the newly discovered IP-to-MAC pairing for future use.

<br/>

## RARP (Reverse Address Resolution Protocol)

RARP operates in the inverse direction, translating a 48-bit hardware MAC address into a 32-bit IP address.

**The Problem**:

- Historically, diskless workstations or new devices starting up didn't have permanent hard drives to store their own IP address configuration

**How It Works**:

- The client device broadcasts a RARP Request containing its own physical MAC address to the local network.

- A designated RARP server on the network checks its pre-configured database to find the IP address that corresponds to that specific MAC address.

- The server sends a RARP reply back, assigning the IP to the requesting machine.
