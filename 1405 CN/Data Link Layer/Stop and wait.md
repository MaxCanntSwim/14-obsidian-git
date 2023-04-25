# Utopian simplex protocol
```C
frame s;
packet buffer;
while (true) { 
	from_network_layer(&buffer);
	s.info = buffer;
	to_physical_layer(&s); 
}
```

# Stop-and-wait for error-free channel
Receiver sends message indicating it can process another frame
```C
frame s;
packet buffer;
while (true) { 
	from_network_layer(&buffer);
	s.info = buffer; 
	to_physical_layer(&s); 
	wait_for_event(&event);
}
```

# Automatic Repeat ReQuest (ARQ) for noisy channel
ARQ adds **error** **control**:  
- Receiver acks frames that are correctly delivered
- Sender sets timer and resends frame if no ack![[Screenshot 2023-04-25 at 11.56.37.jpg]]
this could cause the receiver to interpret the 2nd 2nd frame is the 3e frame

Second option
add correctness: For correctness, frames and acks must be numbered.
- Else receiver can’t tell retransmission (due to lost ack or early timer) from new frame.
- For stop-and-wait, 2 numbers (1 bit) are sufficient.![[Screenshot 2023-04-25 at 12.01.02.jpg]]
## Piggybacking Acks
frames can be sent in both ways
Receiver appends acknowledgement to own frame![[Screenshot 2023-04-25 at 12.03.46.jpg]]

# Problem
Waste bandwidth by waiting
