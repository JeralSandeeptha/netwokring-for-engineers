# Traceroute

`Traceroute` is a network diagnostic tool that shows the path packets take from your computer to a destination server on the internet. It helps identify where delays or connectivity problems occur.

<br/>

## How it works

When you run a traceroute command, it sends packets with gradually increasing TTL (Time To Live) values.

- TTL = 1 → First router receives the packet, decrements TTL to 0, and sends back an "ICMP Time Exceeded" message.
- TTL = 2 → Packet reaches the second router before expiring.
- TTL = 3 → Packet reaches the third router.
And so on, until the destination is reached.

Each responding router is called a hop.

```bash
traceroute google.com

1  192.168.1.1      1 ms   1 ms   1 ms
2  10.0.0.1         8 ms   7 ms   8 ms
3  203.0.113.5     15 ms  14 ms  16 ms
4  72.14.233.100   20 ms  19 ms  20 ms
5  google.com      22 ms  21 ms  22 ms
```

Interpretation:

- Hop 1: Your home router
- Hop 2: Your ISP's router
- Hops 3–4: Internet backbone routers
- Hop 5: Google's server

The times show the round-trip latency to each hop.

<br/>

## Why use traceroute?

Traceroute can help:

- Find where network delays occur
- Diagnose packet loss
- Identify routing problems
- Determine whether an issue is on your local network, your ISP, or a remote network

<br/>

## Understanding Output

![Image](https://res.cloudinary.com/djgwvmcdl/image/upload/v1781356146/6d2b64ed-392e-4016-9c26-60108a54ced1.png)

- Some routers block or deprioritize traceroute packets, causing `* * *` timeouts.
- A timeout at one hop doesn't always mean there's a problem if later hops still respond.
- Different operating systems use different packet types (`ICMP`, `UDP`, or `TCP`) for traceroute.
