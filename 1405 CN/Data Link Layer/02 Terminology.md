# Classifying services/protocols
## State
information about the status of communication changes over time. 
![[Screenshot 2023-04-25 at 11.12.29.jpg]]
## Connection
communication between two parties is **stateful** (i.e., parties maintain state)
![[Screenshot 2023-04-25 at 11.14.26.jpg]]
- agreement on initial state
- exchange of state information (e.g., in the header)

## Connection-oriented vs. connectionless
Connection-oriented service/protocol: 
- establish connection (agree on initial state)
- communicate (data and state)
- release connection (stop storing state)
connectionless service/protocol: just send data

# Evaluating networks and protocols
## Latency/propagation delay
Latency from A to B: time between the moment a very short message leaves machine A until it arrives at machine B (i.e., between A sending and B receiving)

$t_1$: Message arrives at B
Latency: $t_{1} - t_{0}$

### Round trip time (RTT)
round trip time of A and B: time between aA sending a very short message to B and getting a very short response back. 
$t_{3}$: Message arrives at A
Latency: $t_{3} - t_{0}$
Processing time is said to be negligible. 
![[Screenshot 2023-04-25 at 11.20.29.jpg]]

## Transmission time/Delay
Time it takes A to transmit a message, i.e., time between first bit leaves A and when last bit leaves A
$t_1$: A sends last bit
Latency: $t_{1} - t_{0}$

## Bandwidth (in networking)
Maximum rate at which data can be sent between A and B
Measured in **data/time**
Examples:
bps (also: b/s, bits/s): bits per second
MB/s: Megabytes per second

Throughput: actual rate of sending
Goodput: actual rate of sending payload (this is less then the actual throughput, since the payload is not the only thing being send)
