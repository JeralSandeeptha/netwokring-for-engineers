# 3 Way Handshake

A `TCP 3-way handshake` is `a method used in a TCP/IP network to create a reliable, connection-oriented session between a client and a server`.

Before any real data is transferred, this exchange ensures both devices are synchronized, agree on starting sequence numbers, and are ready to communicate.

<br/>

![Image](https://miro.medium.com/v2/resize:fit:1400/format:webp/1*lc-DeGiEV-EVifZ_i_uSJw.png)

**Step 1 (SYN)**: In the first step, the client wants to establish a connection with a server, so it sends a segment with `SYN(Synchronize Sequence Number)` which informs the server that the client is likely to start communication and with what sequence number it starts segments with

**Step 2 (SYN + ACK)**: Server responds to the client request with `SYN-ACK` signal bits set. `Acknowledgement(ACK)` signifies the response of the segment it received and `SYN` signifies with what sequence number it is likely to start the segments with

**Step 3 (ACK)**: In the final part client acknowledges the response of the server and they both establish a reliable connection with which they will start the actual data transfer

[Read more about this topic](https://medium.com/@mrjamzee002/understanding-the-tcp-three-way-handshake-an-introduction-with-wireshark-demo-6d70834a6352)
