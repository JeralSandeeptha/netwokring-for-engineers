# DNS Records

`DNS records` (zone files) are `instructions stored on authoritative servers that act as the internet's phonebook`.

They dictate how traffic is routed and connect human-readable domain names (e.g., example.com) to machine-readable IP addresses

<br/>

## Core Record Types

| Record Type | Function | Value / Example |
| :--- | :--- | :--- |
| **A Record** | Maps a domain to an IPv4 address. | `192.0.2.1` |
| **AAAA Record** | Maps a domain to an IPv6 address. | `2001:db8::1` |
| **CNAME Record** | Forwards an alias to another domain name. | `www.example.com` → `example.com` |
| **MX Record** | Directs email to your mail server. | `mail.example.com` (with priority) |
| **TXT Record** | Stores text information (used for domain verification and security). | `v=spf1 include:_://google.com ~all` |
| **NS Record** | Delegates a domain's zone to a specific set of name servers. | `ns1.example.com` |

<br/>

## Key Components

- **Name**: The subdomain or root domain the record applies to.
- **Type**: The record category (e.g., `A`, `CNAME`, `TXT`).
- **Value / Data**: The destination (e.g., an IP address or hostname).
- **TTL (Time to Live)**: The length of time (in seconds) that a server caches the record before querying for an update.
