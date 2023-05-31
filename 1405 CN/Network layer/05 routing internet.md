# IP address prefix
ip/x (x being a number between 0 and 32)
IPs that have first x bites in common with ip
Alternatively , you can give the subnet mask, which corresponds to 32 bits such that
- first x bits are 1 (network mask)
- other bits are 0 (host mask)

# Classless Inter-Domain Routing (CIDR)
Forward to router that can find rout for given IP ![[Screenshot 2023-05-30 at 11.22.23.jpg]]
![[Screenshot 2023-05-30 at 11.22.46.jpg]]

# Intra- and Inter-Domain Routing
Intra-domain routing: the network owner can decide on the routing protocol
- common choice: Open Shortest Path First (OSPF)
- OSPF is a link state protocol
- Can be compared with a hiearchy for large networks
Inter-domain routing: Border Gateway Protocol (BGP)
- Path vector protocol
- Supports arbitrary policies put in place by ISPs, Companies or countries