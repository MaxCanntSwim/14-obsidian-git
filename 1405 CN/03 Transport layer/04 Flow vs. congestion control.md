![[Screenshot 2023-06-24 at 13.52.20.jpg]]

# Flow control
![[Screenshot 2023-06-24 at 13.53.56.jpg]]window size originally in bytes
Now scale factor to be able to have more unacknowledged bytes
![[Screenshot 2023-06-24 at 13.56.12.jpg]]

## TCP window size Silly-window syndrome
![[Screenshot 2023-06-24 at 13.57.22.jpg]]

# Congestion control
![[Screenshot 2023-06-24 at 14.06.11.jpg]]
If both parties want to use ECN:
End host sending SYN: set ECE and CWR in SYN
Other end host: set ECE but not WR flag in SYN-ACK

## ECN congestion signal
Router marks IP packet as discussed
After receiving a packet with congestion signal: 
- Receiver sets ECE flag in next segment S
- Sender sets CWR flag in next segment after receiving S to signal they received signal and adjust the congestion window

**What is happening when too much congestion**
Both network layer and transport layer are responsible for congestion control. 
the transport layer controls the offered load
![[Screenshot 2023-06-24 at 14.10.59.jpg]]

**Unknowns**
	Available bandwidth
	network topology
	other clients

## Dynamically adjust bandwidth using trial and error
![[Screenshot 2023-06-24 at 14.12.57.jpg]]

# How does TCP combine the two windows?
TCP takes the minimum of the 2 windows since we don't want to overload the receiver or the network. 

## How to start
### 'slow' start 
![[Screenshot 2023-06-24 at 14.23.07.jpg]]
Stop slow start if
- threshold congestion window size reached
- congestion signal
in case of threshold switch to increasing by constant value (additive increase)

#### TCP Tahoe
![[Screenshot 2023-06-24 at 15.33.39.jpg]]

#### TCP Reno
(= TCP Tahoe + fast recovery)
![[Screenshot 2023-06-24 at 15.35.07.jpg]]

#### Cubic TCP
- congestion signal reduces window to 70% of its value
- Congestion window is cubic function since last congestion signal
- Linux/MacOS
#### Compound TCP
- Combines TCP Reno with delay measurements to estimate queuing delay on routers
- reduces sending rate if delays are high
- Windows