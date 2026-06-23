# HTTP

- Hyper Text Transfer Protocol
- Application layer protocol

---

## HTTP Request

![Image](../../images/http-anatomy.png)

![Image](../../images/http-request.png)

<br/>

## HTTP Response

![Image](../../images/response-anatomy.png)

![Image](../../images/http-request.png)

<br/>

## HTTP Versions

### HTTP 1.0

![Image](../../images/http-1.png)

- New TCP connection for each request
- Slow
- Buffering / Chunking (transfer-encoding:chunked didn’t exist in HTTP 1.0)
- No multi-homed websites (HOST header)
- No long polling

### HTTP 1.1

![Image](../../images/http-1.1.png)

- Persisted TCP Connection
- Low Latency & Low CPU Usage
- Streaming with Chunked transfer
- Pipelining (disabled by default)
- Proxying & Multiple websites on single IP

![Image](../../images/http-1.2.png)

Pipeline is disable by default and we can enable that
In the pipeline way order should be critical
Even when images are ready to server for client, still server holds until html ready to serve

### HTTP 2

![Image](../../images/http-2.1.png)

![Image](../../images/http-2.2.png)

Uses the same TCP conenction and it's a persistent TCP connection until gets the response back

Requests and responses are working concurrently

Pros:
● Multiplexing over Single Connection (save resources)
● Compression (Headers & Data)
● Server Push
● Secure by default
● Protocol Negotiation during TLS (ALPN)

Cons:
● TCP head of line blocking
● Server Push never picked up
● High CPU usage

![Image](../../images/http-2.3.png)

### HTTP 3

`HTTP3` means that `HTTP` + `QUIC` protocols

![Image](https://miro.medium.com/v2/resize:fit:1400/format:webp/1*0TQSYkzjmBTC086Qyk-47g.png)

![Image](../../images/http-3.png)

# Pros

- 1 step handshake with TLS (one round trip)
- Has congession control
- has a connection (every datagram labled with connectionID)
