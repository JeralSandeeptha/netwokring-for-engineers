# TCP Flags

There are `Flags` that include the TCP packets

**SYN (Synchronize)**: Initiates a connection. It synchronizes sequence numbers between the sender and receiver.

**ACK (Acknowledgment)**: Confirms receipt of packets. Almost all packets sent after the initial SYN packet have this flag turned on.

**FIN (Finish)**: Gracefully terminates a connection. It signals that the sender has no more data to send.

**RST (Reset)**: Abruptly terminates a connection. Used when an unrecoverable error occurs or a packet arrives for a closed port.

**PSH (Push)**: Forces data delivery. It tells the receiving operating system to pass data to the application immediately rather than waiting for a buffer to fill.

**URG (Urgent)**: Prioritizes specific data. It tells the receiver that the data pointed to by the "Urgent Pointer" field should be processed first.

---

**NS (Nonce Sum)**: Protects routing integrity. It prevents receivers from lying about network congestion to unfairly gain more bandwidth.

**CWR (Congestion Window Reduced)**: Confirms speed reduction. It tells the receiver that the sender received the congestion warning and slowed down.

**ECE (ECN-Echo)**: Flags network bottlenecks. It alerts the sender that intermediate routers are overloaded and data transmission must slow down.
