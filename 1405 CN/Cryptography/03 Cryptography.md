# Definitions
**Cryptosystem**: set of algorithms that guarantee security properties
**(Cryptographic) key**: parameters that determines which algorithm to use
**Cryptography**: creating cryptosystems
**Cryptanalysis**: breaking cryptosystems
**Cryptology**: **cryptanalysis** and **cryptography** together

# Encryption
**Cipher**: cryptosystem for encryption
**Plaintext**: original message M
**Ciphertext**: Original message after an encryption process$$C=Enc(K1,M)(or:C=Enc_{k1}(M))$$
C is the ciphertext when the plaintext M is encrypted using key K1
Decryption: $$M=Dec(K2,C)(or:M=Enc_{k2}(C))$$
for a key K2.

## Kerchoff's Principle
Security should not depend on the secrecy of the algorithm, only on keys
- Enc, Dec publicly known

# Algorithms
## Substitution ciphers
![[Screenshot 2023-05-15 at 12.04.59.jpg]]
## Transposition ciphers
Transposition ciphers reorder the message. 
![[Screenshot 2023-05-15 at 12.06.08.jpg]]

## One-Time pad
Approach: 
1. Create random bit string as key (=one-time pad)
2. Convert message to bit string
3. XOR both strings to obtain cipher
![[Screenshot 2023-05-15 at 12.25.21.jpg]]

# Symmetric-key encryption
Encryption and decryption uses the same key. 
![[Screenshot 2023-05-15 at 12.09.34.jpg]]
Two types of symmetric-key encryption algorithms
- Stream ciphers: apply encryption to each bit
- Block ciphers: divide input in blocks and encrypt blocks
