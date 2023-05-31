Networks vary in protocols they use
- Maximal packet size may vary
	- i.e., be less than $2^{16}-1$
Potential reasons for using a lower packet size: 
- Maximal size is ethernet frame size (1500B)
- Buffers of routers too small to handle big packets
	- need to split packets when routing via networks with lower MTU
MTU = Maximal transmission unit of network

# Nontransparent fragmentation
Gateway of network with smaller MTU divides packet in fragments
Destination reassembles![[Screenshot 2023-05-30 at 11.35.45.jpg]]

# Avoid packet fragmentation MTU discovery
Gateway to network with low MTU tells sender to split packet and discards too big packet![[Screenshot 2023-05-30 at 11.37.34.jpg]]

# Fragmentation in IPv4
identification: identifier for fragments of a packet
DF: dont fragment => use MTU discovery
MF: more fragments to follow
fragment offset: number of 8-byte blocks send in previous fragments

# Fragmentation in IPv6
Routers do not fragment IPv6 packets 
MTU discovery van be used
Source then adds an extension header for fragmentation
Next header in fixed header could be reference to fragmentation extension header