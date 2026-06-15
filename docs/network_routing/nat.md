# NAT / Network Address Translation

`Network Address Translation (NAT)` allows multiple devices in a private network to access the internet using a single public IP address

It helps conserve IPv4 addresses and hides internal systems for added security

- Translates private IP addresses into public IP addresses and vice versa
- Reduces IPv4 shortage by allowing multiple devices to share one public IP
- Hides internal network addresses from external networks
- Uses port mapping (PAT) to manage multiple device connections simultaneously

![Image](https://media.geeksforgeeks.org/wp-content/uploads/20250203170255888522/7.jpg)

<br/>

## How This Works

NAT ways to function is listed as below:

- A device sends a request, reaches the NAT enabled router.
- Router replaces the private IP with its public IP and assigns a unique port.
- NAT stores this mapping in the NAT table.
- When the server responds, NAT uses the stored entry to send the packet to the correct internal device.

<br/>

## Advantages

- Conserves public IPv4 addresses
- Allows multiple devices to share a single public IP
- Hides internal IP addresses from external networks
- Improves privacy by masking internal network structure

## Disadvantages

- Breaks end-to-end connectivity
- Can cause issues with VoIP, gaming, and peer-to-peer applications
- Adds processing overhead on the router
- Makes direct peer-to-peer communication more complex
