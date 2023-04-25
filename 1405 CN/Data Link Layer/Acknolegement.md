Cumulative Acknowledgments

Acknowledgment cumulatively acknowledges all frames up to the number specified in the ack

E.g.: Ack 4 acknowledges all frames up to 4; not necessary to send ack for retransmitted frame 2 and frame 3, which was received out of order = Saves messages
=> (Can be used to deal with messages of varying sizes when size part of ACK, as we will see when discussing the transport layer)

# Realizations of NAK
1.  ﻿﻿﻿Only acknowledge that frame missing (e.g., duplicate acks)  
	    => Do NOT acknowledge which subsequent frame has been received 
	    => Timeout for subsequent frame can still be triggered
1.  ﻿﻿﻿Acknowledge frame is missing and that specific frame has been received  
    => Stop timer and do not trigger timeout/retransmission
Case 1 more common in internet protocols
We will assume Case 1 unless stated otherwise