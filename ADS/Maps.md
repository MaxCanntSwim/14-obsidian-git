Maps map values to a nother value, 
```java
public interface Map<K, V> {
	int size();
	boolean isEmpty ();
	V get (K key);
	V put (K key, V value);
	V remove (K key);
	/* more operations in the book */
}
```
![[Screenshot 2023-01-08 at 15.17.27.jpg]]
there are ways to deal with collisions: 
- **Separate** chaining: have a **secondary** container/ map in each **bucket**
- **Open** addressing: **reuse** other **free** buckets when collisions occur

## Hash functions
To calculate some interger from the information provided. 
## components
### HashCode
This calculates an int from the key. 
### Compress
This will display the results. 
### Conclusion
| name     | opperation      | result                             |
| -------- | --------------- | ---------------------------------- |
| hashCode | Key -> int      | Ruby -> 62(sum int of the letters) |
| compress | int -> {0, N-1} | 62 -> 10 (modulus 26)                                   |

It is smart to split these two functions because, if it turns out you need a different modulus in the compress, you are able to only change the compress. 