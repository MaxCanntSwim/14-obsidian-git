
# Anomaly detection
## Classification
Key ingredient: 
- Maximize negative/outlier space
- Minimize positive/normal space
### Isolation forest
- Repeat N times:  
- Randomly pick a feature f  
- Split the f uniformly at randomly between \[min, max] - Continue until all leafs contain singletons

- The path length to reach a leaf is the isolation score

- Average this length over all trees to get the anomaly score

- Intuition:  
- isolating anomalies is easier because only a few conditions are needed to separate those cases from the normal observations
### Analysis
- Advantage  
	- Can be used in unsupervised setting  
	- Models can be understood  
	- Computationally inexpensive when testing

- Drawback  
	- Make assumptions about data distribution
		- Where is the origin? Is it normal or anomalous? 
		- Intuitively less appealing
## Nearest neighbour
key assumption: 
*normal points have close neighbours while anomalies are located far form other points*

Two-step approach
1. **Distance-based**:
	- compute neighbourhood for each data record
2. **Density-based**:
	- Analyse the neighbourhood to determine whether data record is an anomaly or not
### Distance based outlier detection
NN approach
- for each datapoint d, compute the distance to the d-th nearest neighbour $d_{k}$
- Sort all datapoint according to the distance to $d_{k}$
- outliers are points that have the largest distance $d_{k}$ and therefore are located in the more sparse neighbourhoods
- Usually datapoints that have top n% distance $d_{k}$ are identified as outliers
not suitable for datasets that have models with varying density
### Density-based outlier detection
**Local outlier factor (LOF)**
Compute local reachability density (lrd) of data example q as **inverse** of the average reachability distance based on MinPts(k) nearest neighbours of data example q $$lrd(q)=\frac{MinPts}{\sum\limits_{p}reach \_ dist_{MinPts}(q,p)}$$
**lrd(q) = low → large avg. dist**
**lrd(q) = high → smal avg. dist**

Compute LOF(q) as ratio of average local reachability density of q's k-nearest neighbours and local reachability density of the data record q $$LOF(q)=\frac{1}{MinPts}\cdot\sum\limits_{p}\frac{lrd(p)}{lrd(q)}$$
### Analysis
- Advantage  
	- Can be used in unsupervised setting  
	- Do not make any assumptions about data distribution 
	- Intuitively appealing, uses distances

- Drawbacks  
	- Computationally expensive (when testing)  
	- Requires distances, all disadvantages of distances apply...
## Spectral
Analysis based on eigen decomposition of the data
PCA (principal component analysis)
- orthogonal transformation to reduce dimension
- most data patterns are captured by the several principal vectors
Key idea
- find combination of attributes that capture bulk of variability
- reduced set of attributes can explain normal data well
- but not necessarily explain the outliers
several methods use principal component analysis
- Top few principal components capture variability in normal data
- Smallest principal component should have constant values
- outliers have variability in the smallest component
![[Screenshot 2024-01-28 at 14.44.48.jpg]]

### Analysis
- Advantage  
	- Useful for modeling feature interactions (multivariate data)
	- Computationally efficient (use graphic cards!)

- Disadvantage
	- Based on the assumption that anomalies and normal instances are distinguishable in the reduced space
	- Does not take context into account
	- PCA is sensitive to outliers...

