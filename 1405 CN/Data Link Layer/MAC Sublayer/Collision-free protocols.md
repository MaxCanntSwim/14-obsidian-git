# Token ring
## Assumption: 
Stations are arranged in a ring (e.g. with a cable connection between any two stations on the ring)
## Algorithm
Pass 'token' around the ring 
A station with the token may send data

# Bit-map protocol
## Assumption: 
Static and known stations with a common notation of slots
## Algorithm
Setup: **Enumerate** stations
In the contention period, each station is **assigned** a **slot** to transmit **the bit 1** if they have something to send
In the **transmission** period, all stations that **indicated** they have data, **send** one frame
**Order**: **increasing** order of station **numbers**![[Screenshot 2023-05-02 at 11.09.46.jpg]]

# Binary countdown
## Assumptions:
Static and known stations that have distinct priorities
Collision corresponds to binary OR of bits send at the same time
## Key idea: 
Of the stations that **want** to **send** a frame, the one with the **highest** **priority** will![[Screenshot 2023-05-02 at 11.12.22.jpg]]
## Algorithm: 
Setup:
For **N** stations, assign priority **0** (lowest) to **N-1** (highest)
**Express** priority as **binary** numbers
**Contention** period:
If **wanting** to send, the station **sends** **bits** of priority starting with the **most** **significant** bit
If **1** is received when **0** was sent, the station **stops** and **waits** for a **new** round![[Screenshot 2023-05-02 at 11.17.01.jpg]]

