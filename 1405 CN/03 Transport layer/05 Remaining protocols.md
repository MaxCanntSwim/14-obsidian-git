# TCP drawbacks
Silly window syndrome
Due to handshake, it may take long until you can send data
Head-of-line blocking

## Head-of-line blocking
TCP buffers out-of-order segments
assumes that all segments dependent on each other
Applications can have different (independent) streams of data

### QUIC
UDP + error control + flow/congestion control
QUIC has a connection and streams
A connection can have multiple streams, identified by a stream identifier
In-order delivery is guaranteed per stream => solves head-of-line blocking

**Three-way handshake**
Optional 0 round trip time connection resumption: No handshake needed when previous connection existed
Congestion control: default CUBIC, other possible
Flow control: same window principle as TCP but both on a connection and stream level