# Flow Control

If we send data segments one by one it will very slow process

![Image](https://res.cloudinary.com/djgwvmcdl/image/upload/v1781390114/7af71e8a-25e3-4a45-b6ec-07152bfd26c3.png)

So it's not a ideal solution.

Can we send multiple segements at a time? `Yes of course`. We can like below

![Image](https://res.cloudinary.com/djgwvmcdl/image/upload/v1781390296/ee89ed70-1a56-439d-9b46-f67d03d66fe8.png)

It will send one `ACK` for all the data.

But the question is `how much segments can we transmit at a time`? We assume 3 segements B can handle. If it is then fine but it's not? How can we know that?

![Image](https://res.cloudinary.com/djgwvmcdl/image/upload/v1781390523/a3d869f7-5e1c-4272-97be-35ffd20aa9a1.png)

This is the **Flow Control**

To manage this `TCP` has a special property called `Window Size` like below image

![Image](https://res.cloudinary.com/djgwvmcdl/image/upload/v1781390682/dfffe878-f2d9-4fae-9371-b64f23f5d06a.png)

So in every acknowledgement, it is updating the window size number which they can handle

![](https://res.cloudinary.com/djgwvmcdl/image/upload/v1781390845/5d455f13-f072-428a-8026-5a7793e4221c.png)

This is more likely controlling by `RECEIVER` with updating `Window Size`

but

There is a way called `Sliding Window` and it is mainly controlling by `SENDER` which is it defines how many data should it send

![Image](https://res.cloudinary.com/djgwvmcdl/image/upload/v1781390989/45f07f83-0b96-4fb6-81af-c0b06e628ed1.png)

There can have a more feature in TCP which is `Window Scaling` for scale the receiver's window size because it's too small

![Image](https://res.cloudinary.com/djgwvmcdl/image/upload/v1781391331/a28bde49-795c-4c8e-ad6f-0a49c19fdb7b.png)

but this scaling factor is initiated only once which is during handshake

How it looks in the Three-Way Handshake:

- `Packet 1 (SYN)`: Client tells Server, "My initial receive window is X."
- `Packet 2 (SYN-ACK)`: Server tells Client, "Received. My initial receive window is Y."
- `Packet 3 (ACK)`: Connection is ready. Both sides now know exactly how much data they can safely send

[READ MORE ABOUT WINDOW SCALING](http://networklessons.com/network-fundamentals/tcp-window-size-scaling)