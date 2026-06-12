# Protocols

Network protocols are rules that govern how devices communicate and share data.

They are categorized into three primary functions

- Communication (data exchange)
- Management (network control)
- Security (data protection)

## Categories

### 1. Communication Protocols

These govern how devices exchange data across networks, acting as the fundamental building blocks of internet connectivity.

**Transmission Control Protocol (TCP)**: Ensures reliable, ordered, and error-checked delivery of packets by establishing a connection first.

**User Datagram Protocol (UDP)**: A faster, connectionless alternative that prioritizes speed over reliability; used for real-time applications like video streaming and gaming.

**Internet Protocol (IP)**: Responsible for addressing and routing data packets so they reach the correct destination (e.g., IPv4, IPv6).

### 2. Network Security Protocols

These protect data against unauthorized access, ensuring integrity and authentication during transit.

**Transport Layer Security (TLS)**: The modern successor to SSL, providing secure and encrypted communication over computer networks.

**Secure Shell (SSH)**: Used to securely access and control remote devices, protecting the connection with strong cryptography.

**VPN & IPsec**: Virtual Private Network (VPN) and Internet Protocol Security create secure, encrypted tunnels for transmitting data over public networks.

### 3. Network Management Protocols

These oversee network operations, allowing administrators to monitor, configure, and maintain performance.

**Dynamic Host Configuration Protocol (DHCP)**: Automatically assigns dynamic IP addresses and network configurations to devices as they connect to a network.

**Simple Network Management Protocol (SNMP)**: Used for monitoring, configuring, and managing devices on IP networks.

**Internet Control Message Protocol (ICMP)**: Facilitates error reporting and operational information exchange (like the "ping" command used to test host reachability).

### 4. Application Protocols

These protocols operate at the top of the stack, facilitating direct services for end-user applications.

**Simple Mail Transfer Protocol (SMTP)**: Manages the sending and routing of outgoing emails.

**File Transfer Protocol (FTP)**: Used for the movement of large files between systems on a network.

**IMAP & POP3**: Internet Message Access Protocol and Post Office Protocol allow users to access, read, and manage emails on a mail server.

**Hypertext Transfer Protocol Secure (HTTPS)**: The foundation of World Wide Web data exchange, utilizing encryption to safely transfer hypertext between web browsers and servers.

### 5. Routing Protocols

These define the rules and paths that routers use to discover networks and determine the most efficient path for data traffic.Open Shortest Path First (OSPF): A link-state routing protocol used to find the best path for packets within a single large enterprise network.Border Gateway Protocol (BGP): The core routing protocol of the internet that manages how packets are routed between different internet service providers.Routing Information Protocol (RIP): An older distance-vector protocol that uses hop count as a routing metric to find the path to a destination.

### 6. Internet of Things (IoT) Protocols

These are designed specifically for low-power, resource-constrained smart devices operating over low-bandwidth networks.

**Message Queuing Telemetry Transport (MQTT)**: A lightweight messaging protocol that uses a publish/subscribe model for smart home and sensor data.

**Constrained Application Protocol (CoAP)**: A specialized web transfer protocol for use with constrained nodes and networks in IoT systems.

**Zigbee / Z-Wave**: Wireless mesh network protocols designed for low-power, short-range communication between smart home devices.

### 7. Industrial Automation Protocols

These provide reliable communication between factory hardware, programmable logic controllers (PLCs), and machinery.

**Modbus**: A simple, open master/slave protocol used to transmit signals from instrumentation and control devices back to a main controller.

**Profinet / Profibus**: High-speed automation standards used for data exchange in industrial manufacturing environments.

**EtherNet/IP**: An industrial network protocol that adapts the Common Industrial Protocol to standard Ethernet architecture.

### 8. Storage Area Network (SAN) Protocols

These enable high-speed, dedicated block-level data access between servers and enterprise storage devices.

**Fibre Channel (FC)**: A high-speed network technology primarily used to connect computer data storage to servers in datacenters.

**Internet Small Computer Systems Interface (iSCSI)**: An IP-based storage networking standard for linking data storage facilities over standard Ethernet networks.

**Fibre Channel over Ethernet (FCoE)**: Encapsulates Fibre Channel frames over Ethernet networks, allowing storage and IP traffic to share the same cables.
