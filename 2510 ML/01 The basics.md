- objects, features, measurements, datasets and feature space
- Traditional pattern recognition: classification
- Class posterior probabilities and Bayes' rule
- Bayes' classifier and Bayes' error
- misclassification costs
___
# Generalization
We don't want to just describe the data, we want to predict for new, unseen data. 
___
**Training set**
All examples are labeled 
set is used for training/developing our system

**Test set**
These examples cannot be used to train our system
examples do not have to be labeled
When labels are available, we van objectively evaluate our system

## Features
we have to encode objects
typically encoded by defining features
![[Screenshot 2024-01-20 at 14.44.15.jpg]]

## Datasets
When we measure the features of many objects we obtain a dataset
![[Screenshot 2024-01-20 at 14.45.39.jpg]]

### How to define features
- Features reduce and give a specific view of the object, the user is responsible for this
- Good features allow for pattern recognition
- Garbage in, garbage out
- Other (than feature vector) approaches of defining objects are: 
	- dissimilarity approach
	- structural pattern recognition (graphs)
- Feature approach is very well developed, other approaches are still more research.

# Pattern recognition pipeline
![[Screenshot 2024-01-20 at 14.54.09.jpg]]

# Classification
Given a feature and a training set, where is the blue class?
![[Screenshot 2024-01-20 at 14.56.19.jpg]]

## Class Posterior probability
- for each object we bant to estimate p(y | **x**)
![[Screenshot 2024-01-20 at 15.09.39.jpg]]
this way we are able to classify new incoming objects

## Description of a classifier
Several ways to describe a classifier
- if $p(y_{1} | \vec{x}) > p(y_{2} | \vec{x})$  then assign to $y_{1}$ otherwise $y_{2}$
- if $p(y_{1} | \vec{x})-p(y_{2} | \vec{x})>0$ 
- if $\frac{p(y_{1} | \vec{x})}{p(y_{2} | \vec{x})}>1$
- if $\log{p(y_{1} | \vec{x})}-\log{p(y_{2} | \vec{x})}>0$

# Bayes' theorem
- posterior prob is hard to estimate
- often functional form of class distributions can be assumed
- using Bayes' theorem $$p(y | \vec{x})=\frac{p(\vec{x}|y)p(y)}{p(\vec{x})}$$
- Class (conditional) distribution $p(\vec{x}|y)$
- class prior                                    $p(y)$
- (unconditional) data distribution $p(\vec{x})$
- posterior probability                    $p(y | \vec{x})$

![[Screenshot 2024-01-20 at 15.25.31.jpg]]

![[Screenshot 2024-01-20 at 15.25.50.jpg]]

## Classification error

The error is calculated using the following formula: $$p(error)=\sum\limits^{C}_{i=1}p(error|y_{i})p(y_{i})$$
![[Screenshot 2024-01-20 at 15.46.07.jpg]]
Bayes' error $\epsilon^{*}$ is the minimum error: typically >0!!
we do not have true distributions and can not obtain this
The Bayes' error does not depend on the classification rule that you apply, but on the distribution of the data
In general you can not compute Bayes' error if
- you don’t know the true class conditional probabilities
- the (high) dimensional integrals are very complicated