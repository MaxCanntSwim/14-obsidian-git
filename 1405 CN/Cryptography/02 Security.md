# Goals
**C**onfidentiality: only authorized parties have access to information/system

**I**ntegrity: it is guaranteed that data has not been manipulated. (Includes authentication, nonrepudiation)

**A**vailability: the system/data is there when you need it

# Attacker model
Malicious parties have goals and limitations
- Attacker model
Generally, some parties are assumed to be honest
- Trusted parties

# Attacker types
**Passive** (Eve): Observes, but does not manipulate
**Active** (Malory): Manipulates (and observes)

**External**: not a participant
**Internal**: participant

**Local**: present in part of system
**Global**: presents in whole system

**Static**: behaviour stays the same
**Adaptive**: behaviour changes based on new information

### Computation power
There are two options to consider
- unlimited computational power
	- protocols that protect against this are called **Information-theoretically secure protocols**
	- these are very in-efficient
- Polynomially bounded computational power
	- **Computationally secure protocols**
	- a lot more efficient

### Dolev-Yoa model
Attacker is polynomially bounded and can 
- overhear
- modify
- drop
- replay
- delay
- create
messages in the system. 

## Note
Attacker model does not contain attack strategy, since there could be thousand of different strategies. 