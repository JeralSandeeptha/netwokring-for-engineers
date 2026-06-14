# File Descriptor

A `file descriptor` is just a small integer handle that a process uses to access something managed by the OS.

**The Request (Top Arrow)**:
    - App1 on Laptop 1 (10.0.0.1) wants to talk to an SSH server (AppX) on Laptop 2 (10.0.0.2).
    - Laptop 1 generates a file descriptor linked to local port 5555 and sends a SYN packet targeting remote port 22.

**The Response (Middle Arrow)**:
    - Laptop 2 receives the packet on port 22. Its operating system creates its own local file descriptor to track this specific client (10.0.0.1:5555).
    - It replies with a SYN/ACK packet from port 22 back to port 5555.

**The Established Connection (Bottom Arrow)**:
    - Laptop 1 sends the final ACK packet, completing the TCP Three-Way Handshake.

## Why the File Descriptor Matters Here

Whenever `App1` wants to send data to Laptop 2, it does not need to repeatedly specify the IPs or ports. It simply writes data to its assigned integer (the File Descriptor). The operating system looks at its internal table, sees that the descriptor points to the 10.0.0.1:5555 -> 10.0.0.2:22 socket pair, wraps the data in the correct TCP/IP headers, and transmits it.
