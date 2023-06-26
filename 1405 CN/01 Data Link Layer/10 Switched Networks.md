![[Screenshot 2023-05-09 at 10.59.18.jpg]]

# Hubs
Hub: device connecting multiple (ethernet) devices
Has input/output ports: Signal at one port goes to all other ports
**Hubs are on the physical layer**
**They make all the cables act as one long cable**

# Switch (Bridge)
Use MAC addresses to forward frames between machines such that frame only deliver to intended destination
**Switches are on the data link layer**
![[Screenshot 2023-05-09 at 11.08.23.jpg]]
## Backwards learning
Frames have source and destination information:
	From: A
	To: W
Switch keeps a (hash) table that maps addresses to port numbers. e.g., 
	A-> (port) 1 
	X-> (port) 3 
	Y-> (port) 3
Initially, this table is empty
### Algorithm
```java
On receiving frame m on port i { 
	if(table.lookup(m.From) !=i){
		table.put(m.From,i) 
	}
	if (table.lookup(m.To) != null){ 
		forward to table.lookup(m.To)
	} else {  
		broadcast (excluding i)
	} 
}
```

### Dynamics
Devices move and hence ports change, so the switch might have incorrect/outdated information.
**Solution**
Also keep track of 'time last seen' (=last time switch received message) for each MAC address

Periodically, remove all entries where ‘time last seen’ is too long ago (more than a minute or so)

# Redundancy
*Without any protocols other than backwards learning, redundancy can cause a frame to be forwarded forever.*

You might have more cables than you strictly need to maintain a functional network when hardware failure happen![[Screenshot 2023-05-09 at 11.20.23.jpg]]
## Endless loop example
![[Screenshot 2023-05-09 at 11.20.57.jpg]]
A is removed from hash tables of switches
B believes it still exists
They keep sending since A can not be found
## Spanning tree protocol
Only uses some of the cables such that:
- Graph formed by used cables has no loops
- all parties can be reached (i.e., graph connected)
=> Spanning tree
### Algorithm
Switch with smallest address becomes leader
Other nodes choose parent that offers best* path to the root
*Best could be: shortest, lowest latency, highest bandwidth*
![[Screenshot 2023-05-09 at 11.26.49.jpg]]

### Algorithm song
I think that I shall never see  
A graph more lovely than a tree.  
A tree whose crucial property  
Is loop-free connectivity.  
A tree which must be sure to span.  
So packets can reach every LAN.  
First the Root must be selected  
By ID it is elected.  
Least cost paths from Root are traced In the tree these paths are placed.  
A mesh is made by folks like me  
Then bridges find a spanning tree.

Musical performance: https://www.youtube.com/watch?v=iE_AbM8ZykI