# Client-side
@MessageMapping("???") receives messages sent to /app/???

@SendTo("/topic/???") sends messages to ???

### Example 
```java
@MessageMapping("/quotes") // listens to /app/quotes
@SendTo("/topic/quotes") // sends whatever the method returns to /topic/quotes
public Quote addMessage(Quote q) {
	add(q);
	return q;
}
```



to make the websockets work as intended, subscribe to current board. 

when adding cards or list send update to correct board

use `SimpMessagingTemplate` to be able to send messages from normal REST requests

Decision have to be made about what to do with the deletion of boards while a different client is also connected



