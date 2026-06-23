# QUIC Protocol

`QUIC` is a transport layer network protocol designed to make web communication faster and more reliable

In short

```
HTTP/2 = TCP + TLS (multiple handshakes, higher latency)
HTTP/3 = QUIC (single handshake with TLS + Transport, low latency)
```

![Image](https://sec-consult.com/fileadmin/_processed_/7/4/csm_sec-consult-c-protocol_stacks_branded_718db6c550.webp)

![Image](https://lh3.googleusercontent.com/o62Ohn1Ppxna6zz0NtavqRyetjryOj-81Sz4bRt3U8lURVblk5RKOaCcf57i6BkmprremePJpq_sQcxfJiuA4wJBmRp3pR4BS1P-yiT6UNUPvnBeP_rLz9bvHxFE15kuNBM2hpE)

<br/>

## Why QUIC was Created

Before QUIC, web communication mostly used TCP (Transmission Control Protocol). TCP ensures reliable delivery of packets but at the cost of extra round trips during connection setup. When a client (like your browser) connects to a server:

- It sends a SYN (synchronize) request.
- The server replies with SYN-ACK.
- The client responds with ACK.

That’s three round trips before any real data is transferred. If the connection is secure (HTTPS), another round trip is required for TLS/SSL certificate verification - adding even more delay. This means that even before your web page starts loading, your browser has already spent valuable time "saying hello" to the server.

It's doing single handshake combining transport + security. So very fast

<br/>

## How QUIC Works

QUIC operates in the transport layer, directly on top of UDP. It’s connectionless by nature, but QUIC adds reliability through:

- Packet sequencing
- Acknowledgments
- Loss recovery
- Encryption (built-in TLS 1.3)

| Protocol | Round Trip Time | Example Latency |
| :--- | :--- | :--- |
| HTTP/2 (TCP/IP) | 3–4 round trips | ~284 ms |
| HTTP/3 (QUIC) | 1 round trip | ~261 ms |

<br/>

## Pros

- **Low Latency**: Uses UDP with a single handshake - faster startup.
- **Built-in Security**: Integrates TLS 1.3 for end-to-end encryption.
- **Multiplexing Support**: Multiple data streams in one connection (no TCP "head-of-line blocking").
- **Easier Adoption**: Runs on UDP, already supported by most networks.
- **Connection Migration**: Even if the IP changes (like switching from Wi-Fi to mobile), the session continues seamlessly.

## Cons

- **Limited Browser Support**: Not all browsers or servers fully support QUIC yet.
- **Debugging Challenges**: Traditional TCP monitoring tools don’t work directly with QUIC.
- **Complex Flow Control**: Managing congestion and flow control over UDP is trickier than over TCP.
- **Different Congestion Behavior**: QUIC’s congestion control behaves differently than TCP, which can cause inconsistencies in some network conditions.
