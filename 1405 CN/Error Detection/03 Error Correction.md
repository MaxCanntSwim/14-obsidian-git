# Parity Blocks
Arrange message in table and compute one parity bit per column and row. The flipped bit can be identified as the one for which both column and row do not have a correct result. Parity blocks are also referred to as two-dimensional parity checks. 
## Algorithm
### Preparation
The sender and receiver have to agree on whether odd or even parity is used. Furthermore, they have to decide on the number **r** of rows and the number **c** of columns. If **odd** parity is used, **r** and **c** have to be **either** both **even** or both **odd**. The **number** of bits in the **message** has to be $m=r*c$ (dividing a message into multiple blocks of the correct size and applying padding might be necessary, which we do not discuss in detail). 
### Sender
The sender may apply some pre-processing to have a message of exactly $m=r*c$ bits. 
1. divide into r blocks of length c
2. Enumerate columns form 0 to c-1 and the rows from 0 to r-1
	1. compute parity for each row and column. 
3. Column parity bits of all entries in column **i** written in the cell in row **r** and column **i**
4. Row parity bits of all entries in row **j** written in cell in row **j** and column **c**
5. The entry in column **c** and row **r** is the parity bit for both row parity and column parity bits
### Receiver
1. If all parities are as expected, the receiver assumes that the transmission was error-free. They remove the parity bits and process the message.
2. If exactly one column and one row parity is not as expected, then they assume that the bit in the corresponding row and column has been flipped in transmission. They flip the bit, remove the parity bits, and process the message.
3. Any other mismatch of parities indicates that there was an error but the error cannot be uniquely identified as it has to be caused by more than one bit flip. The receiver requests retransmission.

## Analysis
The amount of redundancy is r+c+1 bits per m-bit message: one parity bit per row, one parity bit per column, and the lower right corner. The minimal values for r and c is $\sqrt{m}$, meaning that the amount of redundancy is bound by O($\sqrt{m}$). 

This algorithm will be able to detect and correct 1 bit-flip. They may ont be able to correct 2 bit-flips if they are in the same row or column, but they will be able to detect them. Four bit-flips may not be detectable. Parity blocks are useful for detecting (but not correcting) burst errors as well. Similar to parity words, the error is likely to only affect one row, so that the parity checks for the affected columns are not as expected. 