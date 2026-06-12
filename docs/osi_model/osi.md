# OSI Model

- We wanted a standardize way to transfer data between different computing devices over a network
- The `Open Systems Interconnection` `(OSI)` model is a `7-layer conceptual framework` developed by the `International Organization for Standardization` `(ISO)`

<br />

![Image](https://github.com/JeralSandeeptha/netwokring-for-engineers/blob/main/images/osi.png?raw=true)

![GIF](https://media.geeksforgeeks.org/wp-content/uploads/20241111182857579134/OSI-Model.gif)

![Image](https://res.cloudinary.com/djgwvmcdl/image/upload/v1781278815/29bed629-9f30-4f5e-b4b9-8737dc35999c.png)

<br />

## Layers

![Image](https://res.cloudinary.com/djgwvmcdl/image/upload/v1781286181/d6a1dcbf-2ce7-4401-92a5-18025f37b5c1.png)

<br/>

![Image](https://github.com/JeralSandeeptha/netwokring-for-engineers/blob/main/images/osi_sender.png?raw=true)
![Image](https://github.com/JeralSandeeptha/netwokring-for-engineers/blob/main/images/osi_receiver.png?raw=true)

<br />

## Memorization Way

```bash
All People Seems To Need Data Processing
```

<br />

## Layers Indepth

| Layer                  | Working                                                                                 | Protocol Data Unit (PDU)         | Protocols                     |
| ---------------------- | --------------------------------------------------------------------------------------- | -------------------------------- | ----------------------------- |
| **Physical Layer**     | Establishes physical connection between devices and transmits raw bits over the medium. | Bits                             | USB, SONET/SDH                |
| **Data Link Layer**    | Provides node-to-node delivery and error detection/correction.                          | Frames                           | Ethernet, PPP, PPTP           |
| **Network Layer**      | Handles logical addressing and routing of data between different networks.              | Packets                          | IP, ICMP, IGMP, OSPF          |
| **Transport Layer**    | Ensures end-to-end communication, segmentation, flow control, and error handling.       | Segments (TCP) / Datagrams (UDP) | TCP, UDP, SCTP                |
| **Session Layer**      | Establishes, manages, and terminates communication sessions between applications.       | Data                             | RPC                           |
| **Presentation Layer** | Translates, encrypts, and formats data for the application layer.                       | Data                             | TLS/SSL, MIME                 |
| **Application Layer**  | Provides network services directly to end-user applications.                            | Data                             | FTP, SMTP, DNS, DHCP, NetBIOS |

<br />

## How to access these layers in real world

### 1. Browser Inspect (Layers 5, 6, and 7)

The browser's Developer Tools (Network Tab) sit inside the application itself. It only cares about the final data payload.

- **Application Layer (L7)**: You see HTTP methods (GET, POST), URLs, API requests, and cookies.
- **Presentation Layer (L6)**: The browser automatically decrypts SSL/TLS for you so you can read JSON, XML, HTML, and images in plain text.
- **Session Layer (L5)**: You see HTTP authentication, active cookies, and individual WebSocket or Server-Sent Events streams.

### 2. Wireshark (Layers 2, 3, and 4)

Wireshark captures raw packets straight off your network card before the operating system or browser processes them. It shows you the physical reality of the wire.

- **Transport Layer (L4)**: This is where you see TCP sequence numbers, SYN/ACK handshakes, UDP ports, and packet retransmissions.
- **Network Layer (L3)**: You see IPv4/IPv6 source and destination addresses, TTL (Time to Live), and routing protocols.
- **Data Link Layer (L2)**: You see MAC addresses, Ethernet frames, and VLAN tags.

<br />

## Encapsulation and Decapsulation

When you send a message, it undergoes a transformation process as it travels down and then back up the stack

`Encapsulation (Down the Stack)`: As data moves from Layer 7 to Layer 1, each lower layer wraps the data received from above with its own control information, known as a Header. Layer 2 also appends a Trailer containing error-checking data.

`Decapsulation (Up the Stack)`: The receiving machine reads the raw bits at Layer 1. It strips away each layer's header one step at a time, processes the instructions, and passes the remaining data upward until the pure application data reaches the destination software.

```bash
[SENDER]                                           [RECEIVER]
Layer 7: Data                                      Layer 7: Data

      |                                                  ^
      v                                                  |
Layer 6: Data                                      Layer 6: Data

      |                                                  ^
      v                                                  |
Layer 5: Data                                      Layer 5: Data

      |                                                  ^
      v (Encapsulation)                     (Decapsulation) |
Layer 4: [L4 Header] + Data                        Layer 4: Data (Header stripped)

      |                                                  ^
      v                                                  |
Layer 3: [L3 Header] + [L4 Data]                   Layer 3: L4 Data (Header stripped)

      |                                                  ^
      v                                                  |
Layer 2: [L2 Header] + [L3 Data] + [L2 Trailer]   Layer 2: L3 Data (Header/Trailer stripped)

      |                                                  ^
      v                                                  |
Layer 1: 0110100101101011 (Raw Bits) ------------> Layer 1: 0110100101101011 (Raw Bits)
```

<br />

## Real-World Deep Dive

### Loading a Webpage

Here is how the 7 layers execute sequentially when you type `https://example.com` into your browser:

- `Layer 7 (Application)`: Browser initiates an `HTTP/HTTPS` GET request protocol
- `Layer 6 (Presentation)`: The connection establishes a secure `TLS`/`SSL`, encrypting your upcoming traffic
- `Layer 5 (Session)`: A persistent logical connection is opened between your browser process and the server process.
- `Layer 4 (Transport)`: The browser maps the traffic to destination port 443 (HTTPS) and chooses a `TCP handshake` to ensure reliable, connection-oriented packet tracking
- `Layer 3 (Network)`: The destination domain maps to an IP address via DNS, and your computer adds the source and destination IP addresses to route packets out of your local network
- `Layer 2 (Data Link)`: Your machine packages the packets into local Ethernet or Wi-Fi frames, adding your router's default gateway MAC address as the immediate next hop.
- `Layer 1 (Physical)`: The frames convert into radio waves (Wi-Fi) or light pulses (fiber optics) to physically travel across the globe.

**NOTE**: First automatically do the TCP 3 way handshake and verify the connection/ create a road in transport layer. Then in the presentation layer, TLS handshake creates a secure tunnel on top of that road

## Modern Way

- [TCP/IP Model](./tcp_ip.md)
- [This is how host to host communication works](./host_to_host.md)
