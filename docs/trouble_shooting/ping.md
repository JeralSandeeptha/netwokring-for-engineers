# Ping

The `ping` command is a network troubleshooting tool used to test whether a device can communicate with another device over a network (such as the Internet or a local network).

<br/>

## What Ping Does

When you run `ping`, your computer sends small `ICMP Echo Request packets` to a target host and waits for `ICMP Echo Reply packets` in return.

If replies are received, it shows:

- Whether the destination is reachable
- How long the communication takes (latency)
- Whether packets are being lost

```js
Pinging google.com [142.250.190.14] with 32 bytes of data:
Reply from 142.250.190.14: bytes=32 time=25ms TTL=117
Reply from 142.250.190.14: bytes=32 time=24ms TTL=117
Reply from 142.250.190.14: bytes=32 time=26ms TTL=117
Reply from 142.250.190.14: bytes=32 time=24ms TTL=117
```

<br/>

## Understanding Output

![Image](https://res.cloudinary.com/djgwvmcdl/image/upload/v1781355343/9b41719b-7291-443d-9282-a50f6a315d49.png)

**time**

```bash
time=25ms
```

The round-trip time (RTT) for a packet to travel to the destination and back.

- < 20 ms → Excellent
- 20–100 ms → Good
- 100–200 ms → Noticeable delay
- 200 ms → High latency

**TTL (Time To Live)**

```bash
TTL=117
```

Limits how many network devices (routers) a packet can pass through before being discarded. It helps prevent packets from circulating forever.

**Packet Statistics**

Example:

```bash
Packets: Sent = 4, Received = 4, Lost = 0 (0% loss)
```

- **Sent**: Packets transmitted
- **Received**: Replies received
- **Lost**: Packets that never returned

Packet loss can indicate:

- Network congestion
- Faulty cables
- Wi-Fi issues
- Server problems
