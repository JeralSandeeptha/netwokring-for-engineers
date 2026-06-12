# IP

`IP` stands for `Internet Protocol`.

Responsible for addressing and routing data packets so they reach the correct destination.

Layer 3 which is network layer protocol

<br />

## IP Packet Anatomy

● The IP Packet has `headers` and `data sections`
● IP Packet header is `20 bytes` (can go up to 60 bytes if options are enabled)
● Data section can go up to `65536 bytes (65kb)`
● Packets need to get fragmented if it doesn’t fit in a frame
● Two types of IP Packets `IPv4` and `IPv6`

<br />

![Image](https://res.cloudinary.com/djgwvmcdl/image/upload/v1781294864/e7b91706-814c-49d5-b520-8881f4beb28d.png)

**1. Version (4 bits)**

- Indicates the IP version.
- For IPv4 packets, this value is always 4.

**2. IHL (Internet Header Length)**

- Tells the length of the header (not the data).
- Measured in 32-bit words.
- Minimum value is 5 (means 20 bytes, no options). Can go up to `60 bytes`

**3. DSCP (Differentiated Services Code Point)**

- Used for Quality of Service (QoS).
- Helps routers prioritize traffic (e.g., video calls vs file downloads).

**4. ECN (Explicit Congestion Notification)**

- Helps detect network congestion without dropping packets.
- Routers can mark this field instead of discarding data.

**5. Total Length**

- The full size of the packet (header + data).
- Maximum is 65,535 bytes.

**6. Identification**

- A unique ID for each packet.
- Used when a packet is split into fragments so they can be reassembled correctly.

**7. Flags (3 bits)**

Control fragmentation:
- `DF (Don’t Fragment)` → packet must not be split
- `MF (More Fragments)` → more fragments are coming
- One bit is reserved (unused)

**8. Fragment Offset**

- Shows where this fragment belongs in the original packet.
- Helps reassemble data in correct order.

**9. Time To Live (TTL)**

- Limits how long a packet can live.
Each router reduces this value by 1.
- If it reaches 0, the packet is dropped (prevents infinite loops).

**10. Protocol**

Indicates the next-level protocol inside the packet:
- TCP = 6
- UDP = 17
- ICMP = 1

**11. Header Checksum**

- Used to detect errors in the header only.
- If corruption is found, the packet is discarded.

**12. Source IP Address**

- The IP address of the sender.

**13. Destination IP Address**

- The IP address of the receiver.
- Options (optional field)

**14. Options**

- Rarely used.
- Only present if IHL > 5.
- Can include things like security, timestamps, or debugging info.

**15. Data (Payload)**

This is the actual content being carried:
- TCP segment
- UDP datagram
- or other data

<br />

## Comparison

| Field                          | IPv4    | IPv6              |
| ------------------------------ | ------- | ----------------- |
| Version                        | ✓       | ✓                 |
| IHL                            | ✓       | ✗                 |
| TTL                            | ✓       | ✗ (Hop Limit)     |
| Header Checksum                | ✓       | ✗                 |
| Fragment Offset in base header | ✓       | ✗                 |
| Address Size                   | 32 bits | 128 bits          |
| Options                        | ✓       | Extension Headers |
