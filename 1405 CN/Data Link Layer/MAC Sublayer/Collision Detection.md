you can **detect** collisions **after** a frame has been **received** (error detection, error control)
**Depending** on the medium, you might be able to **detect** them **during** **transmission** as well
**Stop sending if there is a collision to save time and bandwidth**

# CSMA with collision detection
Carrier-sense is a **necessary** but **not** **sufficient** condition for collision detection.
Contention period: Decide who sends next
Transmission period: Station that has been selected in the contention period sends a frame

## Contention slots
The contention period consists of slots
In each slot, some of the stations start to send.
If there is a collision, they stop. Then, they
1. wait a random number of slots  
2. check if the channel is free
3. try sending it again

## How long does it take to detect a collision?
The maximum time it takes for a signal to travel between two stations sharing the medium: ∆

**A** **starts** sending at time **t**  
**B** might **start** sending until **t+∆-𝜀** 
**B** **detects** a collision and **stops**  
**A** only detects **collision** at **t+2∆-𝜀**

**Contention slots have to be of duration 2∆**
