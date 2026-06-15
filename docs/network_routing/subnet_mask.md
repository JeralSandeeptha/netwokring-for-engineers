# Subnet Mask

A `subnet mask` is a 32-bit number used by a device to split an IP address into two distinct parts: the network address and the host address. It essentially acts as a filter that tells a computer which part of the IP address represents its "neighborhood" (the subnet) and which part represents its specific "house" (the device itself)

**This helps to identify whether that machine local or not**

```bash
255.255.255.0
```

If subnet mask is similar then those are in the same network.
Otherwise those are remote

<br/>

## How Devices Use It

A computer uses the subnet mask every single time it wants to send data. It follows a quick three-step mental checklist to decide where to send a packet:

**Check Destination**: The computer looks at the destination IP address of the data packet.

**Apply Mask**: It applies its own subnet mask to that destination IP to extract the destination's Network ID.

**Make the Decision**:

- `Same Network?` If the destination Network ID matches the computer's own Network ID, the destination is local. The computer uses ARP to send the data directly across the local switch.
- `Different Network?` If the Network IDs do not match, the destination is outside. The computer stops trying to reach it directly and instead forwards the packet to the Default Gateway (the router), which handles the external routing.

<br/>

## CIDR Notation (The Shorthand)

You will often see a subnet mask written as a forward slash followed by a number, like `/24`. This is called `CIDR` notation `(Classless Inter-Domain Routing)`. The number simply counts how many 1s are in the mask.

`/24` means twenty-four 1s `(255.255.255.0)`
`/16` means sixteen 1s `(255.255.0.0)`
`/8` means eight 1s `(255.0.0.0)`
