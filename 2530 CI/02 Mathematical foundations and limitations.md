Topics
- CI as optimization
- Fitness functions and fitness landscapes
- Limitations

- Problems and learning
- Formalisation
___
# Optimization
Both learning and evolution can be thought of as a form of 'optimization':
- Optimization in a mathematical sense can be thought of as
	- Maximize F(**𝛉**)
	- Minimize -F(**𝛉**)

Multiple options are valid for the Fitness/error function
For a Regression problem:
- SSE (Sum of the squared differences), in which case you want to minimize
For a Classification problem
- Cross-entropy (Difference between two probability distribution)

Fitness might relate to multiple objectives
- A problem may have multiple objectives which define what is “good” (which might not be straightforward to combine):
![[Screenshot 2024-04-13 at 09.51.30.jpg]]

## Measuring
Can be very difficult to define what it means to be "good" in many contexts
- Requires domain knowledge
- Conflicting view
Any choices have consequences

In order to calculate if a given solution is "good", features need to be measured. It assumes that: 
 - Contextual meanings need to reduced to consistent, discrete behaviors
 - There exists a true performance value to be measured
 - Variations in measurements across time and context are measurement errors. 

# Supervised learning
You have a task T to perform, i.e., link inputs x to outputs y in some (unknown) domain E through y

All you know About E is a bunch of examples (experience)
A supervised learning technique implements some form of $$\hat{y}=\gamma(\vec{x};\theta)$$
And learns from examples in E (Training) how to set the parameter vector 𝛉 so that the task T is performed with a performance P. 
Usually, the larger (and more diverse) is E, the better is P
## Supervised learning tasks
- Binary classification
	- Beer or not 
- Multi-class classification
	- Which of *m* types of beer is it?
- Regression
	- How many ml of liquid does the bottle contain?

# Unsupervised Learning
The goal of the machine is to build a model $\gamma$ that can be used for reasoning, decision making, predicting things, communicating
however **y** is not given!

## Unsupervised learning tasks
- Clustering
- Error correction
