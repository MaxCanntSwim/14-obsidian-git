# Range
Terminals (= Station for wireless networks) have a range: Their transmissions are only received by parties within this range
![[Screenshot 2023-05-08 at 11.24.01.jpg]]

# Carrier-sense
![[Screenshot 2023-05-08 at 11.26.08.jpg]]
A can sense if B is sending but not if C is sending 
C can sense if B is sending but not if A is sending 
B can sense if A or C are sending

## Hidden terminal (node) problem
![[Screenshot 2023-05-08 at 11.27.19.jpg]]
A is sending to B
C does not sense it and starts sending to B as well => Collision

## Exposed terminal (node) problem
![[Screenshot 2023-05-08 at 11.29.40.jpg]]
B is sending to A
C could send to D but will not because medium seems in use
C cannot receive responses from D if B is still sending

# Multiple Access with Collision Avoidance (MACA)
Mitigates the hidden node problem and exposed node problem through two extra messages
Request-to-send (RTS):
	Indicates terminal wants to send
	Includes sender and receiver MAC address
Clear-to-send (CTS):
	Indicates terminal is free to receive in response to a RTS
	Includes address of receiver of CTS (=terminal wanting to send)

## Example
**A** wants to send to **B**
**A** sends **RTS**
**B** responses with **CTS** if it is not receiving anything else
**A** sends frame if it has received **B**’s **CTS**
**B** sends **ACK** for frame
Any terminal receiving **CTS** for **A** does not send anything until it receives **ACK** (or maximum delay)
**A** backs off before sending another **RTS** if it does not receive **CTS**

# MACA and collisions
Are there never any collisions of actual frames with RTS/CTS?
Still (at least) one way for collisions to happen
Even if everyone follows the protocol
Even if ranges are of the same size
Check out the following simulator and create a collision: https://www2.tkn.tu-berlin.de/teaching/rn/animations/csma/ (uses CSMA/CA, version of MACA in WiFi)

# 802.11
## Collision detection and error control in 802.11
Terminals cannot detect collisions early because they cannot send and receive at the same time. 
Relies on ACKs to determine if a collision occurred. 
	If ACK is lost, sender assumes frame was lost; retransmits frame
	Stop-and-wait protocol

## CSMA/CA
Uses CSMA/CA, Carrier Sense Multiple Access with Collision **Avoidance**, a **variant** of MACA.
Sender in CSMA/CA informs others of **duration** of transmission to deal with **frames** of **varying** sizes
Network Allocation Field (**NAV**) in **RTS** and **CTS** specifies duration of transmission (includes ACK)
**Terminals** allocate time according to **NAV** and do not send during this period
**Thus**, even if they do not sense transmission, they do not accidentally cause a **collision**

## Example of NAV
![[Screenshot 2023-05-08 at 12.06.36.jpg]]
A's NAV should be a little bit longer since the NAV is a little bit longer than the entire message + ACK

## Random backoffs in CSMA/CA
CSMA/CA uses a **binary exponential backoff**
But it **starts** also with a **random backoff** after others are done **sending**
To **avoid** **multiple** terminals **start** sending at the **same** time
A variant of **p-persistent CSMA (**skip** a certain number of slots instead of skipping each with probability p)
If other terminal **starts** sending **during** backoff, **counting** down slots is **interrupted** and **taking** up **after** transmission

### Example
![[Screenshot 2023-05-08 at 12.11.16.jpg]]

## Modes
### Infrastructure mode
![[Screenshot 2023-05-08 at 12.15.25.jpg]]

### Ad-hoc networks
![[Screenshot 2023-05-08 at 12.16.05.jpg]]

## Frames
![[Screenshot 2023-05-08 at 12.18.42.jpg]]
3de address for intermediaries

### Addresses
![[Screenshot 2023-05-08 at 12.20.10.jpg]]
1. from receiver to sender 
2. dont know
3. dont know
4. router to router, needs address of both routers and the sender and receiver

# 802.16
Broadband wireless: meant for metropolitan large-area networks
comes with inbuilt encryption
allows requesting different types of services

# 802.15.1
Bluetooth (now: bluetooth special intrest group standards):
meant for personal area networks (headsets, local file transfer)

# 802.15.4
meant for implanted networks in the human body