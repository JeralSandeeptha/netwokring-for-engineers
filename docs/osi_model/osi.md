# OSI Model

- We wanted a standardize way to transfer data between different computing devices over a network
- The `Open Systems Interconnection` `(OSI)` model is a `7-layer conceptual framework` developed by the `International Organization for Standardization` `(ISO)`

<br />

![Image](https://github.com/JeralSandeeptha/netwokring-for-engineers/blob/main/images/osi.png?raw=true)

![GIF](https://media.geeksforgeeks.org/wp-content/uploads/20241111182857579134/OSI-Model.gif)

<br />

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
