# Congession Control

In between those two devices, there can be more devices in that network. So with `Flow Control` we can only find `Sender` and `Receiver` window sizes. How about the others between them? For that we use this.

![Image](https://res.cloudinary.com/djgwvmcdl/image/upload/v1781392766/281d0be5-6a48-41eb-a209-c2bb0c61aff3.png)

This congession window owned by `SENDER`

There are 2 algorythmes for this:

- **Slow Start**
    - Slow start but go fast
    - `CWND` + 1 MSS for every `ACK`

- **Congession Avoidance**
    - Once slow starts kicks its threshold this is getting started
    - `CWND` + ` MSS after complete RTT

`CWND` (Congession Window) slowly getting increasing for every `ACK` up until it similar to `R` (Receivers Window)

![Image](https://res.cloudinary.com/djgwvmcdl/image/upload/v1781393776/d2a93f03-8af7-4231-b045-b82513c9c048.png)

If hits the Congession Window threshold then swicth it to Congession Avoidance algorythm

![Image](https://res.cloudinary.com/djgwvmcdl/image/upload/v1781394312/aca0784f-d4a4-4aee-b055-957e2cf062be.png)

![Image](https://res.cloudinary.com/djgwvmcdl/image/upload/v1781394382/1b596aaa-49f6-47af-8630-3df5d4e23164.png)
