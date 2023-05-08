Physical layer sends bits
- send data bit by bit
- need extra information for reliability
- group bits and add information per group/unit
name of the unit including additional bits: Frame

# Summary: Protocols for lost frames
Utopian simplex protocol: nope
Stop-and-wait for error-free channel: adds confirmations but does not resend
Stop-and-wait with ARQ 1 (no numbering): resends but cannot deal with lost acks
Stop-and-wait with ARQ 2 (numbering): works but low throughput
Sliding window with Go-back-N: works but unnecessary retransmission
Sliding window with Selective Repeat: works fine

# Structure
**Header**: e.g., sender, receiver, version
**Trailer**: error detection / correction bits

Header and Trailer: **fixed** length and **structure**
Data: **variable** length (with **max** and **min**)

## Example
![[Screenshot 2023-04-25 at 11.05.57.jpg]]
preamble: alternating zero and ones, for clock sync
dest: MAC address
source: MAC address

# Questions data link layer
How do we do the error detection and correction?


How do we detect if (whole) frames are lost?

How do we detect if parts of frames are lost?

How do we know when a frame ends and the next one starts? (it's all just bits at the physical layer)

What information goes into the header?
=> Will be done with MAC-Sublayer

