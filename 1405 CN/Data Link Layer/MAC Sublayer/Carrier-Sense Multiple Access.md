The sender detects ('sense') if the channel is in use. 

Protocols that apply CSMA:
1. 1-persistent: wait for idle, then send
2. non-persistent: if busy, wait a random amount of time. Try again. 
3. p-persistent: if busy, wait for the next slot. if idle, send with probability p. 

# 1-persistent
![[Screenshot 2023-05-01 at 12.18.38.jpg]]
# Non-persistent
![[Screenshot 2023-05-01 at 12.19.11.jpg]]
# P-persistent
![[Screenshot 2023-05-01 at 12.20.25.jpg]]
# Comparison
![[Screenshot 2023-05-01 at 12.22.50.jpg]]
