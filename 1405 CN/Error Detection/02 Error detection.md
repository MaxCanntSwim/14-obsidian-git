# Parity Bits
Refers to whether a number is odd or even. 
Parity bit appended to a message such that the number of bits in the message is either even or odd. 

## Example
### Preparation
The sender and receiver agree on desired parity
### Sender
The sender has message M. They count the number n of 1s in the message. Then they append one-bit **b** as follows: 
|             | n even | n odd |
| ----------- | ------ | ----- |
| even parity | b = 0  | b = 1 |
| odd parity  | b = 1  | b = 0      |
In other words, they add a bit such that the total number of bits reflects the agreed amount. 
### Receiver
Gets message M' (M'=M + b). They count the number of 1s in M'. 
	If parity is as agreed with the sender, assume the message is correct
		remove the last bit and process the message
	If parity does not match expectation, signal error to retransmit

## Analysis
The amount of redundancy is 1 bit per message of m bits, so the lowest possible redundancy for messages of that size. This comes at the price of being unable to detect an even number of bit-flips as they leave parity unchanged. 
	only suitable if more than 1 bit-flip is highly unlikely

# Parity Words and Internet Checksum
![[parity.svg]]
An alternative interpretation of the algorithm is that the sender appends parity bits such that the first parity bit is the first bit of each block, the second for the second bit of each block, etc. 
## Internet
The internet uses IP and TCP,  a varies from parity words, such that instead of a bitwise XOR, binary addition with carries is used. 

## Note
Checksum is sometimes used to refer to any bits appended to the message for error detection. At other times it is used to refer specially to internet checksum. 

## Example
### Preparation 
Sender and receiver agree on block length **k**, and possibly an algorithm for padding if the message length is not a multiple of $k^{3}$. For parity words, they further agree on parity. 
### Sender
![[sender word.svg]]
### Receiver
![[receiver word.svg]]
## Analysis
The amount of redundancy is k bits per message of m bits. Parity words and internet checksum cannot detect an even number of bit flips that affect the same parity bit/column. 

More precisely, internet checksum can detect if both flips are in the same direction as this changes the sum. if one flip changes a 0 to a 1 and the other changes a 1 to 0, the sum remains unaffected. 

The chance of this happening is lower if the checksum is computed over a small number of bits. 
	For a fixed m, the higher k, the higher the probability of detecting errors
		however also higher redundancy

# Cyclic Redundancy Checks (CRCs)
Sender and receiver agree on divisor **g**. appended bits cause the message to become divisible by **g**. Receiver checks for divisibility. 
CRCs can be extended to allow for error correction as well. 
CRC can guarantee detection of more than two bit-flips regardless of position. 

## Example
### Preparation
Sender and receiver agree on so-called generator **g**, a binary number of length **k + 1** and starting with 1. 
### Sender
The sender executes following steps
1. append **k** zeros to the message **M** to obtain the message **M'**
2. Obtain the remainder **r** by dividing M' by **g**
3. pad **r** from the left with 0s until it is of length **k**
4. Append the padded remainder to the original message **M** to obtain **M''**
5. Send **M''** form step 4 to the receiver

An alternative to step 3 and 4 is to subtract the remainder from **M'**. Since if we subtract the remainder we make the message divisible by **g**. 
### Receiver
Receiver checks if message is divisible by **g**. If not, trigger retransmission. 
	If correct, remove last **k** bits and process the remaining bits

## Polynomial Division
CRCs interpret binary numbers as one-bit coefficients of polynomials, so a number $b_{k},...,b_{0}$ is interpreted as the polynomial $b_{k}x^{k}+b_{k-1}x^{k-1}+...+b_{0}$ . k is the degree of the polynomial. The polynomial arithmetic has the following rules: 
- Addition is the same a subtraction (and the same as bitwise XOR). When two polynomials are added, their coefficients are added. each coefficient is a single bit, either 0 or 1, and the result also has to be a singel bit, thus all three operations are the same
- There are no carries, 101 + 110 = 011 not 1011
- There is no total order. 110 is not bigger than 101. The polynomial degree is similar to an order in terms of division with remainder:
	Dividing a polynomial p of degree $k_{p}$ by a polynomial d of degree $k_{d}$ results in a quotient polynomial q and a remainder polynomial r. The quotient polynomial is of degree $k_{p}-k_{d}$ if $k_{d}≤k_{p}$ and is the zero polynomial otherwise. r is the difference between p and q x d and is at most of degree $k_{d}-1$.
				![[Screenshot 2023-05-08 at 15.49.17.jpg]]
## Analysis
The amount of redundancy is k bits per message. The number of bit flips that can be detected highly depends on the choice of g. If g is chosen carefully, any two bit flips can be detected. The choice of **g** is complicated and requires more mathematical background than we assume for this cours. Thus, we will assume **g** is given. 