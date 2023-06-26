Machines on the internet are identified by their IP address. 
These names are difficult to remember
IP addresses can change aswell
DNS translates human-readable names to IP addresses

![[Screenshot 2023-06-24 at 15.57.41.jpg]]

# Name servers
To translate a domain name to an IP address, you ask a **name server**.
![[Screenshot 2023-06-24 at 16.00.10.jpg]]
Name server configured by **DHCP**. 

## Recursive queries
![[Screenshot 2023-06-24 at 17.19.00.jpg]]

## Iterative queries
![[Screenshot 2023-06-24 at 17.21.32.jpg]]

## Domain resource records
name servers reply with domain resource records. A record can contain: 
1. IPv4 (record type A)
2. IPv6 (record type AAAA)
3. Domain that accepts email (record type MX)
4. Name server for this domain (record type NS)