# Approaches
Traffic overloads router, i.e., arrives faster than it can process
Queue forms at the router
	long delays, potential loss due to insufficient buffer space

## Network provisioning
- Get more bandwidth
	- More paths better routers
	- longterm solution and expensive

## Traffic-aware routing
Choose routes depending on traffic as well as other factors, Include queueing delay into cost used for routing, but make sure that you do not switch to overloading other links. 
Multi-path routing, i.e., splitting traffic over multiple routes is useful
Exact details vary between networks if it's done at all. 

## Admission control
Only allow new traffic flows when it will not cause congestion
Provide information about traffic in advance
Average bandwidth use as well as burst

## Traffic throttling
Send a signal that there is too much traffic Classifying signals: 
1. Precise vs not precise: give concrete rate at which they can send vs just signal that there is congestion without specific rate
2. Explicit vs implicit: send a message vs give an indirect signal
3. End-to-end vs link-by-link: tell only source to slow down vs tell all previous routers+sources to slow down

## XCP: eXplicit Congestion Protocol
Explicit, precise and end-to-end
routers compute precise rate that source can send at
Send message to source with rate
Consists of two parts:
- Congestion control: ensure capacity used
- Fairness control: ensure all flows get fair share