Error detection and correction deal with one or multiple bits flipped during transmission from a sender to a receiver.
An error occurred, which can mean one or more bit-flips. 
Fairly likely to happen with wireless transmission
To this, error detection or correction are applied by data link layer

routers on network layer may introduce bit flips while relaying data, for this the transport layer is responsible. 
![[Screenshot 2023-05-08 at 13.04.57.jpg]]

Error detection: Receiver can detect error but not identify which error occurred
	sender has to be given signal to retransmit message
Error correction: Receiver can identify the exact bit or bits that have been flipped, and thus can solve the error

# Choosing algorithm
Detection and correction only reduce the probability of errors to be forwarded to the next higher layer. 
For this purpose extra bits arre added. The number of additional bits added is referred to as the amount of redundancy. Usually given as additional bits per data amount or percentage of extra data. 

Instead of **Amount of redundancy** the term overhead van be used, this is not a synonym for amount of redundancy, but  a more general term. 
	(refer to any additional bits added to the actual message, e.g., information about the protocol version used or flag bytes that indicate the beginning of a frame on the data link layer)

Things to consider when choosing an algorithm 
- more redundancy -> more errors can be detected
	- more data to be transmitted
- errors known to be rare -> low redundancy
- Error correction -> lower latency
	- for same amount of redundancy
		- correction higher chance of forwarding incorrect message