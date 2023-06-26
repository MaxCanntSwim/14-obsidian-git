Transmission Control Protocol
Provides a reliable end-to-end byte stream over an unreliable network. 
That means: 
- Error detection
- Retransmission
- Flow control
- congestion control

# Header
![[Screenshot 2023-06-24 at 12.12.23.jpg]]
Green: generic information
Blue: message type flags (flag: bit indicating a property only included ones we will talk about)
Yellow: error detection/control
Purple: flow control

**Why do we need header length?** 
	there are options and we need to know where the header ends. 

# TCP checksum
computed over header and payload, same as internet checksum
Segments with invalid checksums are discarded. 
TCP uses a sliding window protocol that triggers retransmission. 
# TCP connection
for each TCP connection, local state consists of
- next sequence number to use
- next ack number to use
- congestion window
- timers for retransmission
# Sequence and ack numbers
![[Screenshot 2023-06-24 at 12.24.28.jpg]]
SYN: connection establishment
ACK: acknowledgement
FIN: connection termination
## purpose of sequence numbers
1. detect missing segments
2. detecting duplicates
3. detecting out of order segments

## Starting connection
Before sending SYN: choose the initial sequence number
When receiving SYN: choose the initial sequence number

**Sequence number:** 
initial own sequence number + number of preciously send bytes
**Ack number:**
initial seq num of com partner + number of previously received bytes

Every data byte **adds 1** to the seq num
SYN and FIN also **add 1** to the seq num
ACKs do **not** increase seq num
**Initial seq num:** 
can be chosen in different ways

### Establish: Three way handshake
![[Screenshot 2023-06-24 at 12.32.22.jpg]]![[Screenshot 2023-06-24 at 12.36.58.jpg]]![[Screenshot 2023-06-24 at 12.43.52.jpg]]
## Connection release
### Asymmetric
![[Screenshot 2023-06-24 at 13.41.05.jpg]]
### Symmetric
![[Screenshot 2023-06-24 at 13.42.35.jpg]]

## Crash
### scenario 1
![[Screenshot 2023-06-24 at 13.45.31.jpg]]
### scenario 2
![[Screenshot 2023-06-24 at 13.45.59.jpg]]

Crash recovery is done on the next layer. 

