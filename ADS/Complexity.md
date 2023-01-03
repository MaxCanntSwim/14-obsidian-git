Complexity is shown as a tightest bound for the function, in [[Big O-notation]]. 
___

## Time complexity
Time complexity is discribed in a function dependent on the imput size to predict the time the algorithm will take, for example: 
```java
public static boolean Method1(int[] distances) {  
	int smaller = 0;  
	for(int i = 0; i < distances.length; i++) {  
	 
		if(distances[i] <= 10) {  
			smaller++;  
		}  
	}  
	int greater = 0;  
	for(int i = 0; i < distances.length; i++) {  
	 
		if(distances[i] > 10) {  
			greater++;  
		}  
	}  
	if(smaller > greater) {  
		return true;  
	} else {  
		return false;  
	}  
}
```
This results in $10n+8$, thus this is $O(n)$, since the tightest bound is $n$.

## Space complexity
Space complexity is a discribed in a function dependent on the imput size to predict the space the algorithm will take, for example: 
```java
public static boolean Method1(int[] distances) {  
	int smaller = 0;  
	for(int i = 0; i < distances.length; i++) {  
	 
		if(distances[i] <= 10) {  
			smaller++;  
		}  
	}  
	int greater = 0;  
	for(int i = 0; i < distances.length; i++) {  
	 
		if(distances[i] > 10) {  
			greater++;  
		}  
	}  
	if(smaller > greater) {  
		return true;  
	} else {  
		return false;  
	}  
}
```
This algorithm has 0 recursive calls, thus the space complexity is $1$. This also means that the Big O for the space complexity is equal to $O(1)$