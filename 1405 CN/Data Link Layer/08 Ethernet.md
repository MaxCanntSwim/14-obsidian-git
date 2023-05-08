# The ambiguity of MACs
MAC address = **media access control address**
unique code for the **network interface controller** of the device

MAC = **message authentication code** (signature)
**Appended** to message to **guarantee** it has not been **tampered** with and is from the **claimed** sender

# CSMA/CD
Ethernet uses 1-persistent CSMA/CD
![[Screenshot 2023-05-08 at 10.58.30.jpg]]
Binary Exponential Backoff (BEP):
Choose number of slots uniformly at random in {0, 1, ...,$2^{i}-1$} where i is the number of failed tries to send the frame. 

# Ethernet and retransmissions
Ethernet retransmit when there has been a collision
## What about bit-flips and lost frames?
Ethernet does not acknowledge and just silently discards anything for which the CRC is incorrect. 
It is a connectionless protocol. 
That is fine because it has few errors and the higher layers can capture those. 

# Ethernet frame structure
## Type/Length
![[Screenshot 2023-05-02 at 12.14.01.jpg]]
if it is a type the value is above **1536**, **600** in **hexadecimal**
this works since the **max length** of the data is **1500** so if it is larger it has to be a type
otherwise it is a length

## preamble
![[Screenshot 2023-05-02 at 12.18.03.jpg]]
final 11 is to signal the end of the preamble. SoF means Start of Message. 

## Addresses
End of frame, it has 12 bytes of absolute silence. 
First 6 bytes is the destination, where we are sending to. 
next 6 bytes is the address we are sending from and where we want the reply to be. 
![[Screenshot 2023-05-02 at 12.20.36.jpg]]

## Data/pad/CRC
![[Screenshot 2023-05-02 at 12.30.06.jpg]]
padding made to make the frame 72 bytes for collision detection
