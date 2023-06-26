User Datagram Protocol
Very thin layer on top of IP. Header provides posts needed to connect to remote applications. 
![[Screenshot 2023-06-24 at 12.01.59.jpg]]
UDP length: bytes in payload/body plus bytes in header (always 8), 65535
UDP checksum: computed over the rest of the header and the payload internet checksum used in IP
data in IP checksum: checksum only for header
data in UDP checksum: checksum for header and actual packet

UDP does not automatically retransmit. It just discards. 
# Segment structure
Header: information about segment grouped in fields
body: content
