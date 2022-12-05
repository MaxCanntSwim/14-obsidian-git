
* P(n) = the invariant holds before of the n-th iteration

* Basis property

* The invariant holds before the first iteration of the loop

* P(1) holds

	* Inductive property

* If the invariant holds before an iteration of the loop, then it also holds before the next iteration

* P(k) →P(k+1) holds for an arbitrary k

	* Falsity of guard

* After a finite number of iterations the guard becomes false and the loop terminates

* Correctness of the post-condition

* The combination of the invariant and the negation of the guard imply that the post-condition holds, thus the program is correct.
[[Miscellaneous]] [[Induction proof]] 