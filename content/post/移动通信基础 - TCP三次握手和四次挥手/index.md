---
title: Mobile Communication - TCP Three-way Handshake and Four-Way Wavehand
subtitle: This article is an explanation of "TCP Three-way Handshake and Four-Way Wavehand".

# Summary for listings and search engines
summary: This article is an explanation of "TCP Three-way Handshake and Four-Way Wavehand".

tags: 
- Mobile Communication

categories: 
- Mobile Communication
date: '2022-04-17'
math: true
---

## Three-way Handshake
- First handshake: the client sends a SYN packet (syn=x) to the server and enters SYN_SEND status, waiting for server confirmation;

- Second handshake: when the server receives the SYN packet, it must confirm the SYN (ack=x+1) of the client and send a SYN packet (syn = y), that is, SYN+ACK packet. At this time, the server enters SYN_RECV status;

- Third Handshake: after receiving the SYN+ACK packet from the server, the client sends an acknowledgement packet ACK (ack=y+1) to the server. After this packet is sent, the client and the server enter the ESTABLISHED state and complete the third handshake.

The packet transmitted during the handshake does not contain data. After the three handshakes, the client and the server formally start to transmit data. In an ideal state, once a TCP connection is established, the TCP connection will be maintained until either of the communication parties actively closes the connection.



## Four-Way Wavehand
Similar to the "three-way handshake" for establishing a connection, disconnecting a TCP connection requires "four-Way Wavehand".

- First wave: the active closing party sends a FIN to close the data transmission from the active party to the passive Closing Party, that is, the active Closing Party tells the passive closing party that I will not send you any more data (for the data sent before the FIN packet, if the corresponding ACK acknowledgement message is not received, the active closing party will still resend the data). However, the active closing party can still accept the data at this time.

- Second wave: after receiving the FIN packet, the passive closing party sends an ACK to the other party, confirming that the sequence number is the received sequence number + 1 (the same as SYN, one FIN occupies one sequence number).

- Third wave: the passive closing party sends a FIN to close the data transmission from the passive closing party to the active Closing Party, that is, to tell the active closing party that my data has been sent and will not be sent to you again.

- Fourth wave: after the active closing party receives the FIN, it sends an ACK to the passive Closing Party, and confirms that the serial number is the received serial number + 1. So far, the fourth wave is completed.
