# Routing goals
To get from A to B:
- optimally using the most cost effective path when assigning each link a cost

# Routing tables
You want to know for every address, on which link to forward the packet. For this we use a routing table![[Screenshot 2023-05-30 at 10.29.19.jpg]]
## Distance vector routing
**Distance vector**: To and cost column of routing table
				Send distance vector to neighbours, who then construct their tables based on it![[Screenshot 2023-05-30 at 10.31.30.jpg]]
**Algorithm**
to determine: routing table of Y
Given Link(Y, I) and distance vectors of all neighbours I
for each destination X
	for each neighbour I 
		Compute Cost(Y, I, X) = Link(Y, I) + Cost(I, X)
	Determine neighbour M with minimal cost
	put (X, Cost(Y,M,X), M) in routing table
![[Screenshot 2023-05-30 at 10.52.56.jpg]]

### Frequency of updates
When to send distance vectors: 
1. periodically
2. Whenever something changes

In addition to cost and line, maintain the path to reach destination in routing table
Include when sending updates
Discard updates with loops

## Link state routing
Does not suffer from count to infinity problem, but requires maintaining knowledge of full network!
1. Routers only send packets with information about their direct neighbours
2. These packets are flooded over the network
3. Routers built an overview of the network using these packets and run a shortest path algorithm
![[Screenshot 2023-05-30 at 11.11.05.jpg]]

## Hierarchical routing
Reducing routing table sizes for large networks. 
Only one entry per network other than own network
![[Screenshot 2023-05-30 at 11.13.03.jpg]]
![[Screenshot 2023-05-30 at 11.13.19.jpg]]
add**x** can be individual addresses or ranges
A checks second column for destination and then forwards to neighbour in first column
