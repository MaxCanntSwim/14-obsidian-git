# Sending a frame
receive data from the network layer
assign data to frames
per frame:
1. write data in the payload field
2. fill in the header
3. compute trailer (over header+data)
4. execute framing protocol (e.g., byte stuffing)
5. Send the frame bit-by-bit to the physical layer

# Receiving a frame
Divide data from the physical layer into frames (using the framing method)
Per frame:
1. execute error detection/correction
2. stop if an error detected
3. otherwise, remove the trailer
4. react to header (e.g., buffer if sequence number unexpected)
5. remove header
6. send data to network layer
7. send ACK to sender (if protocol has ACKs)