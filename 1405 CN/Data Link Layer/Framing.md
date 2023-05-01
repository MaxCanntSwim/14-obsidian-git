# Motivation
Where does one message end and the next begin? 

## Naïve approach
- Delay
	- add a delay after the end of the frame before starting next
		- unused bandwidth
		- requires functionality to measure time
		- multiple parties sending may hide the end of the frame
- fixed length
	- All frames are likely to be resent due to error detection failing
- Byte count
	- every frame starts with a byte count
		- completely fails when the byte count gets flipped

## Effective alg
- Byte stuffing
	- add a special "flag byte" to mark the beginning and end of the frame![[Screenshot 2023-05-01 at 11.06.56.jpg]]
	- escape byte
		- escape byte: if flag byte in normal data, put escape byte in front
			- Also, do that for an escape byte in the data. ![[Screenshot 2023-05-01 at 11.13.02.jpg]]
			- can be inefficient because escaping always adds a full byte
	- Bit flips
		- bit flips can happen in frame and escape bytes (which are NOT included in error detection/correction)
		- The first frame and maybe the second one are discarded (+ retransmitted if protocol is connection-oriented) Remaining frames are received fine
- Bit stuffing
	- key idea: only use one bit for escaping![[Screenshot 2023-05-01 at 11.23.11.jpg]] Example: ![[Screenshot 2023-05-01 at 11.23.47.jpg]]
	- Sender
		- send flag pattern
		- send data bit-by-bit, but add 0  after every three consecutive 1s
		- send flag pattern
	- Receiver
		- ![[Screenshot 2023-05-01 at 11.25.54.jpg]]