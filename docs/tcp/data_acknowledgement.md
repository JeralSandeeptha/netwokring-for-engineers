# Data Acknowledgement

![Image](https://res.cloudinary.com/djgwvmcdl/image/upload/v1781373251/e7259d0c-c579-4be9-b203-327a209031d6.png)

Client send segment and for that server sends an acknowledgement about segment transfered correctly with `ACK` status with segment for relavant sequence

<br/>

---

![Image](https://res.cloudinary.com/djgwvmcdl/image/upload/v1781373195/cd0cdf4a-bd94-43c5-b247-9a2401dd6b4c.png)

We can send multiple segments before acknowledgements of previous segments like top image
So if multiple packets transmitted, then it will send the `ACK` status for last segments number
It means they can do single `ACK` for multiple segments

<br/>

---

![Image](https://res.cloudinary.com/djgwvmcdl/image/upload/v1781373836/962b41a5-faa2-4bfe-b293-c3e45bb76155.png)

When a segment is lost it sends `ACK` only for last successful segement number

Suppose if 2nd segment fails, the receiver sends exactly two acknowledgment packets which are 1 segment ACK and 3rd segement ACK seperately
