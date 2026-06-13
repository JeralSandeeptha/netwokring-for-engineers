# TCP

`TCP` stands for `Transmission Control Protocol`

- connection
- Stateful
- Need a session to send data
- Layer 4 / Transport Layer protocol
- Ability to address process using ports
- Need a handshake
- Lost segments are retransmitted
- Has a sequence and order
- If data lost then again retransmit the data

<br/>

## TCP Anatomy

![Image](https://res.cloudinary.com/djgwvmcdl/image/upload/v1781368588/fd871d1a-efdd-461b-9a3a-cedb3bb972fe.png)

**Source & Destination Ports**: Identify the sending and receiving applications (e.g., port 443 for HTTPS).

**Sequence Number**: Tracks the order of bytes so the receiving device can reconstruct data in the correct order.

**Acknowledgment Number**: Confirms receipt of packets and tells the sender which byte sequence to expect next.

**Data Offset & Flags**:Data Offset tells the computer where the header ends and the actual payload begins.

**Flags**: (NS, CWR, ECE, URG, ACK, PSH, RST, SYN, FIN) manage connection states (like the SYN flag used to start sessions). [READ MORE](./tcp_flags.md)

**Window Size**: Used for `flow control`, telling the sender how much data the receiver can handle before pausing.

**Checksum & Urgent Pointer**: Verifies that the packet header hasn't been corrupted during transmission.

<br/>

## Connection Establishment

In TCP usage, everything depends on a conenction

- For that it is using [TCP 3 Way Handshake](./3way_handshake.md) for establish the connection

After that it maintain the connection. It has several connection statuses. [READ MORE](./tcp_flags.md)

## Data Sending and Acknowledgement

How does devices send and know about data successfully transfered to correct destination or not.
For that they are using `ACK` commands / Acknowledgements.
[Refer More](./data_acknowledgement.md)

## Terminate Connection

In TCP usage, everything depends on a conenction

- For disconnect it is using [TCP 4 Way handshke](./4way_handshake.md) for terminate each other

<br/>

## Use Cases

- Reliable Communication
- Remote Shell
- Database connections
- Web communicaitons
- For bidirectional commuications

<br/>

## Pros

● Guarantee delivery
● No one can send data without prior knowledge
● Flow Control and Congestion Control
● Ordered Packets no corruption or app level work
● Secure and can’t be easily spoofed

## Cons

● Large header overhead compared to UDP
● More bandwidth
● Stateful - consumes memory on server and client
● Considered high latency for certain workloads (Slow start/ congestion/ acks)
● Does too much at a low level (hence QUIC)
    ○ Single connection to send multiple streams of data (HTTP requests)
    ○ Stream 1 has nothing to do with Stream 2
    ○ Both Stream 1 and Stream 2 packets must arrive
● TCP Meltdown
    ○ Not a good candidate for VPN
