- Evolutionary computing (EC)
- Problems that can be modeled with EC methods
- Steps of a genetic algorithm (GA)
- Describe GA operations: Selection, Cross-over and mutation
- Apply
___
# Evolutionary computing (EC)
EC is most commonly used in optimization problems, with a given objective function and a set of constraints. 
___
## Why
EC algorithms are flexible optimization algorithms
- No constraints in the type of variables  
- Works well with non-linear objective functions  
- Insensitive to discontinuities or shape  
- Can be adapted to multi-objective optimization problems 
- In general, requires few assumptions about the problem
## Basic concepts
- **Population**: a set of candidate solutions
- Fitness: criterion for evaluation the goodness of candidates
- **Selection**: process through which solutions are picked for further refinement
- **Reproduction**: process through which new solutions are produced from existing solutions under the assumption that 
	- good solutions, when combined, will likely yield even better solutions(**exploitation**)
	- Unexpected changes in solution (e.g., via mutation) can yield better solutions (**exploration**)

# How to GA
Problem: find the value of x (say, x*) that maximizes the function$$(16x-x^{2})$$
constrained: x is an integer between 0 and 15
## Step 1
Encode the candidate solution x into chromosomes
- since x can only take 16 different values, 4 bits are sufficient to encode any candidate solution
![[Screenshot 2024-04-13 at 21.04.30.jpg]]
## Step 2
Define how the fitness of a candidate solution is measured 
- The fitness is computed on the decoded chromosome in this example$$f(x)=16x-x^{2}$$
## Step 3
Randomly select an initial population of N chromosomes
![[Screenshot 2024-04-13 at 21.06.52.jpg]]

## Step 4
compute the fitness of all chromosomes in the population
![[Screenshot 2024-04-13 at 21.07.55.jpg]]

## Step 5
Pick the chromosomes for reproduction
Example Roulette wheel Selection
![[Screenshot 2024-04-13 at 21.09.10.jpg]]

## Step 6a
With probability $p_{c}$ use the two selected chromosomes to generate offspring
- if no offspring is generated -> cloning
Pick a random cross-over point and swap the bits after that point among the two chromosomes

X2: **0010**, X5: **1100**, cross-over point 1
![[Screenshot 2024-04-13 at 21.11.26.jpg]]
Typical values of $p_{m}≈0.7$  
## Step 6b
With probability $p_{m}$
mutate (flip) the bits in the new chromosomes

Mutation probability is typically small, otherwise leads to instability (and longer search times)
Typical values of $p_{m}$ range between 0.001 and 0.01

## Step 7 
Put the offspring in the new population
## Step 8
Substitute the old population with the new one
## Step 9
Repeat from step 4

## Stop condition
The process stops if:
- A **sufficiently good** solution is found, or
- A predefined number of **iterations** (generations) has been executed

# Hyperparameters GA
Length of the chromosome, L  
- Depending in the precision required for the problem

Population Size, N  
- Larger the search space, larger the N should be

Cross-over probability  
- Generally high, e.g., 0.7

Mutation probability  
- Generally low, e.g., 1/L Or 0.1/L

Number of generations, G  
- Depends on the computational resources available
