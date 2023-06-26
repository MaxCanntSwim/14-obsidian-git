# Internet Protocol (IP)
IP is a connectionless protocol to route data from a source to a destination over multiple networks (with some connection-oriented aspects in v6)
We group data into IP packets or datagrams
	Datagram: 
					"A self-contained, independent entity of data carrying sufficient information to be routed from the source to the destination computer without reliance on earlier exchanges between this source and destination computer and transporting network"

# IP packets
![[Screenshot 2023-05-30 at 09.51.33.jpg]]

## IPv4 header
![[Screenshot 2023-05-30 at 10.16.11.jpg]]
IHL = internal header length (can vary due to options)
Total length = number of bytes in packet including header 
		Maximum is $2^{16}-1=65535$
The Second row = fragmentation: to be discussed later
Time to live = Decreased by 1 whenever forwarded
		If it reaches 0, discard
		Default: nowadays mostly 64
Header checksum = internet checksum over other header fields
								router discard packets with invalid checksums
								Needs to be recalculated whenever forwarded
source/destination address = IP addresses of end hosts

## IPv6 header
fixed header
Extension headers: optional headers e.g., fragmentation
![[Screenshot 2023-05-30 at 10.22.30.jpg]]
Flow label = Group packets and define rules for routers when forwarded them (e.g., priority for videos), default: 0
Payload length = number of bytes of payload plus extension headers
Hop limit = same as time-to-live in v4
