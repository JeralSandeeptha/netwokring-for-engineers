# UDP

`UDP` stands for `User Datagram Protocol`

- Stateless
- No session
- Layer 4 / Transport Layer Protocol
- Ability to address process using ports
- Connectionless
- No handshake
- No congession control
- No flow control
- No packet order
- Less security
- Low bandwidth
- Low latency

The naming breaks down into two core concepts:

**User**: Unlike some protocols that operate purely for system or network administration, UDP is designed specifically to interface directly with the user's applications (like a web browser or video game). It passes messages directly to and from applications via port numbers.

**Datagram**: This is a combination of the words "data" and "telegram". In networking, a datagram is a completely independent, self-contained data packet. Like a physical telegram, a UDP datagram contains all the necessary routing and destination information within itself. The sender just pushes the datagram out into the network and assumes it will reach the destination without establishing a prior connection (handshake) to verify the path.

<br/>

## UDP Packet Anatomy

![Image](https://res.cloudinary.com/djgwvmcdl/image/upload/v1781335322/673c4fce-3867-44d0-bc3b-34ce18ea178c.png)

**1. Source Port (16 bits / Bits 0–15)**

- **What it does**: Identifies the sending application's port number on the source device.
- **Why it matters**: It tells the receiving device where to send reply packets, though it is optional in UDP and can be set to all zeros if no reply is expected.

**2. Destination Port (16 bits / Bits 16–31)**

- **What it does**: Identifies the specific receiving application or service on the destination device.
- **Why it matters**: It ensures the destination operating system delivers the data payload to the correct app (e.g., Port 53 for DNS, Port 123 for NTP).

**3. Length (16 bits / Bits 32–47)**

- **What it does**: Specifies the total size of the entire UDP segment in bytes.
- **Why it matters**: This count includes both the 8-byte UDP header and the variable-length Data section. The minimum value is 8 (a packet with zero data).

**4. Checksum (16 bits / Bits 48–63)**

- **What it does**: Used for error-checking to verify that the header and data were not corrupted during transmission.
- **Why it matters**: If the receiver calculates a checksum that does not match this field, it silently drops the packet. In IPv4, this field is optional, but in IPv6, it is mandatory.

**5. Data**

- **What it does**: Contains the actual application payload being transmitted (e.g., a DNS query or a streaming audio chunk).
- **Why it matters**: Its size is variable, bounded only by the maximum IP packet size limits we discussed earlier.

<br/>

## Pros

- Simple Protocol
- Datagrams are small because header is small
- Use less bandwidth
- Stateless
- Consumes less memory (No state stored in server/client)
- Low latency - No handshake, order, retransmission or garanteed delivery

## Cons

- No Acknowledgement
- No granteed delivery
- Connectionless -> Anyone can send data without prior knowledge
- No flow control
- No congession control
- No ordered packets
- Security -> Can be easily spoofed

---

## Example

```js
import dgram from 'dgram'

const socket = dgram.createSocket("udp4");
socket.bind(5500, "127.0.0.1");
socket.on("message", (msg, info) => {
    
    console.log(`My Server got a datagram ${msg}, from: ${info.address}:${info.port}`)

})
```
