# 4 Way Handshake

`Four-Way Handshake` is the `standard process used to safely and orderly terminate (or tear down) an established TCP (Transmission Control Protocol) connection`

<br/>

![Image](https://media.geeksforgeeks.org/wp-content/uploads/20251106163448590456/initiator.webp)

**Step 1 (FIN from Client)**: The client sends a `FIN` to the server to start closing and enters the `FIN_WAIT_1` state.
**Step 2 (ACK from Server)**: The server acknowledges the `FIN` and the client moves to FIN_WAIT_2.
**Step 3 (Client Waiting)**: The client waits for the server’s FIN while in the FIN_WAIT_2 state.
**Step 4 (FIN from Server)**: The server sends its `FIN` after completing its closing tasks.
**Step 5 (ACK from Client)**: The client acknowledges the server’s `FIN`, enters `TIME_WAIT`, and after a set delay, the connection closes fully.
