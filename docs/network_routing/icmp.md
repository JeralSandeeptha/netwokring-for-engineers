# ICMP

`ICMP (Internet Control Message Protocol)` is a diagnostic protocol that network devices (like routers) use to send error messages and operational information.

It lets devices communicate delivery failures, like when a requested service is unavailable or a packet takes too long to route.

<br/>

## Why it is Needed

The base Internet Protocol (IP) simply moves data from one point to another, but it lacks built-in error checking or diagnostic features. ICMP acts as the network's feedback system. Without it, if a data transmission failed, the sender would never know why or if it even reached its destination.

<br/>

## How it Works

Unlike protocols used to load web pages (like TCP), ICMP is connectionless. This means devices do not perform a "handshake" before sending messages.

**Encapsulation**: ICMP messages are embedded directly inside standard IP packets.

**Error Reporting**: If a router cannot deliver a packet, it drops the packet and sends an ICMP error message back to the original sender.

**Diagnosis**: Diagnostic tools like ping send an ICMP Echo Request and wait for an ICMP Echo Reply to verify if a device is reachable.

<br/>

## Common ICMP Messages

**Echo Request / Echo Reply (Type 8 / 0)**:
Powers the ping command to test latency and reachability.

**Destination Unreachable (Type 3)**:
Alerts the sender that the destination network or host cannot be reached.

**Time Exceeded (Type 11)**:
Tells the sender a packet was dropped because its Time-To-Live (TTL) counter hit zero (commonly used by the traceroute command).

[READ MORE](https://www.geeksforgeeks.org/computer-networks/internet-control-message-protocol-icmp/)

