To sort sequence **S** of **n** keys that are **d-tuples** of radix **N**:
Apply **stable** bucket sort **sequentially**, using a **different** elementary key of the **tuple** at each **iteration**.

**Composite keys**: keys in a sequence S are **d-tuples** of **elementary** keys
key = (k1, k2, ..., kd)
	examples: 
| keys       | tuple des                                    | Alphabet      | Radix(N)           |
| ---------- | -------------------------------------------- | ------------- | ------------------ |
| 0612345678 | phone number is a 10-tuple of decimal digits | {0,1, .., 9}  | 10 possible digits |
| AMS        | airport code is a 3-tuple of capital letters | {A, B, ...,Z} | 26 possible letters                   |

# LSD
Backward (**LSD**: **least**-significant digit first)
![[Screenshot 2023-01-08 at 13.59.18.jpg]]
Bucket sort applied **d** times: O(**d(n + N)**)

## Application
Generally works with keys of **equal-length**.
**Strings** of equal-length (e.g. airport codes).
**Integers** of equal-length (e.g. **integers** using their **bit** representation, **telephone** numbers).

**More**:
**Can** be made to work with **variable**-length keys that **align** right.
**But** needs to either process the keys per **length** or use **padding** with **zeros** on the left.
**Example**: multi-digit integers

**00**40
**000**2
**0**315
**000**8

**Not** really suited for **variable**-length keys that use **lexicographic** order (e.g. **strings** in general).

# MSD
It works, if we apply bucket sort recursively within each bucket formed in the previous iteration!
![[Screenshot 2023-01-08 at 14.05.48.jpg]]

## Application
**Works with keys of different length.**
	**General** strings.
	**Integers** (e.g. because it can make use of their bit representation).
**Can** be faster than **LSD**, since it may **not** need to process all **elementary** keys.
**Overhead** due to recursive calls.
**Improvements: check 3-way radix quicksort.**
