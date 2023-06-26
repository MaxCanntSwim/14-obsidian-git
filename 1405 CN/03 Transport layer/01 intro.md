How do we map network data to applications?
How does UDP realize an unreliable transport layer?
How does TCP realize a reliable transport layer?
- ﻿﻿How does it handle connection establishment and disconnect?
- ﻿﻿How does it handle error control (e.g., retransmission)?
- ﻿﻿How does it handle flow control?
- ﻿﻿How does it handle congestion control?
Are there other transport layer protocols?
# Topics
1. ﻿﻿﻿Addressing
2. ﻿﻿﻿UDP
	- ﻿﻿Segment structure
	- ﻿﻿Error detection
1. TCP
	- ﻿﻿Segment structure
	- ﻿﻿Error detection
	- ﻿﻿Connection establishment and termination
	- ﻿﻿Error control
	- ﻿﻿Flow control
	- ﻿﻿Congestion control
2. Other transport layer protocols

# Mapping data to applications
You typically only have one IP address, but you run several applications using the internet. 
![[Screenshot 2023-05-30 at 12.26.28.jpg]]
TSAP = Transport Service Access Point
NSAP = Network Service Access Point
Internet uses IP addresses for NSAPs and ports for TSAPs

## Port
On the transport layer: virtual space allocated by the operating system to organise network traffic
65535 (virtual) ports numbered from 1 to 65535
Some of them are allocated to standard applications

## Primitives used for addressing
1. ﻿﻿﻿Listen - wait for another process to contact us.
2. ﻿﻿﻿Connect - connect to a process that is **listening**.
3. ﻿﻿﻿Send - send data over the established **connection**.
4. ﻿﻿﻿Receive - receive data over the established **connection**.
5. ﻿﻿﻿Disconnect - release the **connection**.

### Berkeley Socket primitives
1. Socket - create a new communication **endpoint**.
2. Bind - assign a **local address** to the socket.
3. Listen.
4. Accept - passively accept an incoming **connection request**.
5. Connect.
6. Send.
7. Receive. 
8. Close. 

## Process servers
**Example**
Razebary pie, use for 4 different applications. 
Instead of having all the applications live all the time, put them to sleep, and when a message arrives on their port, wake them up. 

## Multiplexing
multiple transport connections over one network data stream
![[Screenshot 2023-05-30 at 12.39.32.jpg]]

## Inverse multiplexing
One transport connection over multiple network data streams
![[Screenshot 2023-05-30 at 12.40.24.jpg]]