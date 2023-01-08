# Complexity
Complexity is shown as a tightest bound for the function, in Big O-notation. 
Tags: #definition 
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

# Big O-notation
Big O-notation means the tightest bound for the function. 
For example, $f(x)=3x^3+2x$
The Big O for this function is $O(x^3)$ 
This needs to hold for some $x=n_0$ and for all $x>=n_0$
Tags: #definition

# Divide-and-conquer
Divide-and-conquer is an algorithmic design pattern consisting of 3 steps:
1. Divide:  
	    **Small** input: **base** case  
		    If input is small (e.g. 1-2 elements), solve problem **directly**.  
	    **Larger** input: **recurrence**  
		    **Divide** the input into **two** or more **disjoint** subsets.
1. **Conquer**: **Recursively** solve the subproblems associated with the **subsets**.
2. **Combine**: Take the **solutions** of the subproblems and **merge** them into a solution to the larger problem.

# Sorting
## key type
**Key type**: keys are used as **indices** into an array, **cannot** be arbitrary **objects**.

## Stable sorting
**Stable sorting**: **preserves** **the relative order** of any two items with the same key.
	For any two items (ki, vi) and (kj, vj) such that Ki = Kj;
	and (ki, vi) precedes (kj, vj), or i < j, in **S** **before** sorting, 
	**then** (ki, vi) also precedes (kj, vj), or i < j, in **S** **after** sorting.

# Decrease-and-conquer
(prune-and-search)
**Prune** away a **fraction** of the **n** elements. **Recursively** solve the **smaller** problem. **Find** solution for **base case** using a **brute-force** method.

