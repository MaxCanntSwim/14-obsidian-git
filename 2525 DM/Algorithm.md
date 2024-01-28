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

# Distance
A distance metric $d(\cdot,\cdot)$ should satisfy the metric properties:
- non negativity: $d(A,B)≥0$
- Identity: $d(A,B)=0 \iff A=B$
- Symmetry: $d(A,B)=d(B,A)$
- Triangle inequality: $d(A,C)≤d(A,B)+d(B,C)$
## Jaccard similarity
measures the overlap between two sets A and B $$J(A,B)=\frac{|A\cap B|}{|A\cup B|}$$
### Applications
- Finding out whether students plagiarized their reports:  
	- If you copy parts of text, Jaccard similarity will be high even after many edits  
- Making sure that Google does not show duplicate results:
	- Remove items that have a Jaccard similarity of nearly one
- Finding similar pieces of malware:  
	- Collect the presence of system calls, cluster using Jaccard
## Euclidean distance
distance between two vectors a and b$$d(\vec{a},\vec{b})=\sqrt{\sum\limits_{d=1}^{D}(a_{d}-b_{d})^{2}}=||\vec{a}-\vec{b}||$$
### When to use
1. continuous data
2. not too many columns
3. magnitude matters
### When to avoid
1. when dealing with high dimensional data
	- curse of dimensionality
2. When dealing with sparse data
	- Zero values are treated as any other
3. When magnitude matter
	- It is not scale invariant! (dist(a, b) ≠ dist(a\*c, b\*c) for constant c)
4. in the case of discrete data
### Euclidean is
- a metric
- invariant to translation  
- dependent on scale  
- sensitive to outliers  
- sensitive to dimensionality - sensitive to sparsity
## Manhattan distance
The absolute difference$$d(\vec{x}, \vec{y})=\sum\limits^{n}_{i=1}|x_{i}-y_{i}|$$![[Screenshot 2024-01-28 at 16.00.10.jpg]]
### When to use
- when outliers are a problem
- When features are incomparable
- When you have many dimensions
## Maximum (Chebyshev) distance
aka chessboard distance$$d(x,y)=max_{i}|x_{i}-y_{i}|$$
### When to use
- Not so clear
- when it makes sense
- when features are incomparable
### When not to use
- Outliers are clearly a problem
## Hamming distance
Distance compare two bit sequences
- Hamming distance counts the number of dissimilar bits![[Screenshot 2024-01-28 at 16.14.48.jpg]]
## Match-based distance
- The problem of high dimensionality is for a large part due to different noise in different dimensions
- This effect becomes less with lower values for p  

- Another approach to lessen this effect is to only perform local distance computations per dimension
- We divide each dimension into k equal sized bins with range \[m, n\], then of two points are in the same bin for dimension d compute: $$PSelect(\bar{X}, \bar{Y},k_{d})=[\sum\limits_{i\,\epsilon\, S(\bar{X}, \bar{Y},k_{d})}(1-\frac{|x_{i}-y_{i}|}{m_{i}-n_{i}})^{p}]^{\frac{1}{p}}$$
- otherwise return 0
## Cosine distance
the angle between two vectors$$d(\vec{a},\vec{b})=1-\cos(\theta)=1-\frac{\vec{a}^{T}\vec{b}}{||\vec{a}||\,||\vec{b}||}$$
does violate the triangle inequality
![[Screenshot 2024-01-28 at 16.43.31.jpg]]
### When to use
comparing bag-of-word vectors of documents
- main advantage: distance does not depend on length of documents! scale invariant
- not translation invariant
### Angular distance
- So technically, the cosine “distance” is not a proper distance metric
- The triangle inequality violation may be resolved by taking the arc-cosine:$$d(\vec{a}, \vec{b})\arccos(\cos(\theta))=\arccos(\frac{\vec{a}^{T}\vec{b}}{||\vec{a}||\,||\vec{b}||})$$
## ISOMAP distance
- Compute kNN for each data point  
- Construct weighted graph: weights = distance 
- Set:
	- ISOMAP distance(p, q) = weight of shortest path from p to![[Screenshot 2024-01-28 at 16.47.44.jpg]]
## Statistical distances
### Kullback-Leibler Divergence
![[Screenshot 2024-01-28 at 21.19.58.jpg]]
- Measures surprise when using Q instead of P
- the Expected value of the log likelihood ratio between P and Q
- The number of extra bits needed to represent samples from P using Q
- Information gain or relative entropy
![[Screenshot 2024-01-28 at 21.22.50.jpg]]
## Edit distance
The edit distance counts the number of operations to go from A to B:
- Substitution of characters 
- Insertion of characters  
- Deletion of characters
# Clustering
## K-means clustering
a good clustering is one for which the within-cluster variation(WCV) is as small as possible
The WVC for cluster k: measure the amount by which the observations within a cluster differ from each other
K-means clustering is to solve this optimisation problem: $$\underset{C_{1},...,C_{k}}{minimize}\lbrace \sum\limits^{K}_{k=1}\frac{1}{|C_{k}|}\sum\limits_{i,i'\epsilon C_{k}}\sum\limits^{p}_{j=1}(x_{ij}-x_{i'j})^{2}\rbrace$$

### How
randomly assign a number from 1 to k, to each of the observations
iterate until the cluster assignments stop changing
- for each of the k clusters, compute the cluster centroid. the  kth cluster centroid is the vector of the p feature means for the observations in the kth cluster
- assign each observation to the cluster with center closest to the observation (defined using Euclidean distance)
### Determine the number of clusters
- based on the sum of squares within the clusters for a solution against the number of clusters
- the optimal number of clusters can be determined by the "elbow criterion"![[Screenshot 2024-01-28 at 22.08.25.jpg]]
## Bottom-up/top-down learning
we do not need to commit to a particular choice of K
Bottom-up or agglomerative clustering
- A dendrogram is built starting from the leaves and combining cluster up to the trunk
Top-down or agglomerative clustering
- A dendrogram is build starting from the root and spitting clusters to the leaves

### How
- Begin with n observations. Treat each observation as its own cluster
- Identify the closest two clusters and merge them 
- Repeat  
- Ends when all points are in a single cluster

### Cluster distance
- The distance between the clusters is called linkage

- Different specifications for linkage  
	- **Single linkage**: Distance between clusters is the distance of the closest points (minimum spanning tree)  
	- **Complete linkage**: Distance between clusters is the distance of the farthest points 
	- **Average linkage**: mean distance between all the points in the two clusters  
	- **Ward distance**: difference between the total within cluster sum of squares for the two clusters separately, and the within cluster sum of squares resulting from merging the two clusters in one cluster
### When to stop
		![[Screenshot 2024-01-28 at 22.16.37.jpg]]
## DBSCAN
Given threshold *t* and radius *e*
![[Screenshot 2024-01-28 at 22.24.16.jpg]]
### How
1. Determine core, border and noise points
2. connect core points within distance *e*
3. find all connected components
4. assign border points to closest connected component
5. return all components as clusters
## Graph-based clustering
1. construct neighbourhood graph G
	- connect points if their distance is below a threshold
	- connect points if they are nearest neighbours of each other
2. Set weight on edges based on the point-wise distance
3. find communities on G using graph mining
4. return the found communities as clusters
### Issues
- Should the observations or features first be standardised/normalized in some way?
    *This influences the distance!*

- Cluster methods use the definition of a distance between observations
    *Which distance to use?*

- How many clusters to choose?  
    - Difficult problem. No agreed-upon method.  
    - Can be determined by **visualizing** the cluster solution
    - 

![[Screenshot 2024-01-28 at 22.33.24.jpg]]