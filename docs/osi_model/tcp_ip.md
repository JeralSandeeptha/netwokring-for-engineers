# TCP/IP Model

The internet is explicitly built on the `TCP/IP` model. The differences between the two frameworks map directly out like this

```bash
As conceptually OSI model is the standard way but in real world / practically these are working related to TCP/IP model
```

## How TCP/IP works related to OSI model

| OSI Model Layer     | TCP/IP Model Layer       | Main Functions                                                                             |
| ------------------- | ------------------------ | ------------------------------------------------------------------------------------------ |
| **7. Application**  | **Application Layer**    | Manages application protocols, user services, and network applications.                    |
| **6. Presentation** | **Application Layer**    | Handles data formatting, encryption, decryption, and compression.                          |
| **5. Session**      | **Application Layer**    | Establishes, manages, and terminates communication sessions (dialogue control).            |
| **4. Transport**    | **Transport Layer**      | Manages host-to-host delivery, flow control, error recovery, and port addressing.          |
| **3. Network**      | **Internet Layer**       | Manages logical routing and global IP addressing across independent networks.              |
| **2. Data Link**    | **Network Access Layer** | Handles local framing, MAC addressing, error detection, and access to the physical medium. |
| **1. Physical**     | **Network Access Layer** | Handles physical hardware interaction, signal transmission, and bit conversion.            |
