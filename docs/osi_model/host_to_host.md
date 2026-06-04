# Host to Host Communication

![Image](https://github.com/JeralSandeeptha/netwokring-for-engineers/blob/main/images/host_to_host.png?raw=true)

- First it check the Subnet Masks (255.255.255.0) and compairs both of them. If both are similar it means they are inside of the same/local network. Then they can directly share the data through MAC address

- If Subnet Masks are not similar, then data sends to the `Default Gateway` which is `Router`. Router has a ip adderss of that each subnet. So via MAC Address it send the data
