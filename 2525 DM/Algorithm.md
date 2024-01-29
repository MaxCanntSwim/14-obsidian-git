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

#### Implementation
```python
from sklearn.ensemble import IsolationForest

def isolation_forest_example(X, n_estimators=100):
    model = IsolationForest(n_estimators=n_estimators)
    model.fit(X)
    scores = model.decision_function(X)
    return scores
```
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
#### Implementation
```python
from sklearn.neighbors import NearestNeighbors
import numpy as np

def nn_outlier_detection(X, n_neighbors=5):
    nbrs = NearestNeighbors(n_neighbors=n_neighbors).fit(X)
    distances, _ = nbrs.kneighbors(X)
    outlier_score = np.sort(distances[:, -1], axis=0)
    return outlier_score

```
### Density-based outlier detection
**Local outlier factor (LOF)**
Compute local reachability density (lrd) of data example q as **inverse** of the average reachability distance based on MinPts(k) nearest neighbours of data example q $$lrd(q)=\frac{MinPts}{\sum\limits_{p}reach \_ dist_{MinPts}(q,p)}$$
**lrd(q) = low → large avg. dist**
**lrd(q) = high → smal avg. dist**

Compute LOF(q) as ratio of average local reachability density of q's k-nearest neighbours and local reachability density of the data record q $$LOF(q)=\frac{1}{MinPts}\cdot\sum\limits_{p}\frac{lrd(p)}{lrd(q)}$$
#### Implementation
```python
from sklearn.neighbors import LocalOutlierFactor

def lof_outlier_detection(X, n_neighbors=20):
    lof = LocalOutlierFactor(n_neighbors=n_neighbors)
    outlier_scores = -lof.fit_predict(X)  # Negative scores indicate outliers
    return outlier_scores

```
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
### Implementation
```python
from sklearn.decomposition import PCA
import numpy as np

def pca_anomaly_detection(X, n_components=2):
    pca = PCA(n_components=n_components)
    X_reduced = pca.fit_transform(X)
    X_reconstructed = pca.inverse_transform(X_reduced)
    anomaly_score = np.sqrt(np.sum(np.square(X - X_reconstructed), axis=1))
    return anomaly_score
```
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
### Implementation
```python
def jaccard_similarity(set_a, set_b):
    intersection = len(set_a.intersection(set_b))
    union = len(set_a.union(set_b))
    return intersection / union
```
### Applications
- Finding out whether students plagiarized their reports:  
	- If you copy parts of text, Jaccard similarity will be high even after many edits  
- Making sure that Google does not show duplicate results:
	- Remove items that have a Jaccard similarity of nearly one
- Finding similar pieces of malware:  
	- Collect the presence of system calls, cluster using Jaccard
## Euclidean distance
distance between two vectors a and b$$d(\vec{a},\vec{b})=\sqrt{\sum\limits_{d=1}^{D}(a_{d}-b_{d})^{2}}=||\vec{a}-\vec{b}||$$
### Implementation
```python
from scipy.spatial import distance

def euclidean_distance(vec_a, vec_b):
    return distance.euclidean(vec_a, vec_b)
```
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
### Implementation
```python
def manhattan_distance(vec_a, vec_b):
    return sum(abs(a - b) for a, b in zip(vec_a, vec_b))

```
### When to use
- when outliers are a problem
- When features are incomparable
- When you have many dimensions
## Maximum (Chebyshev) distance
aka chessboard distance$$d(x,y)=max_{i}|x_{i}-y_{i}|$$
### Implementation
```python
def chebyshev_distance(vec_a, vec_b):
    return max(abs(a - b) for a, b in zip(vec_a, vec_b))
```
### When to use
- Not so clear
- when it makes sense
- when features are incomparable
### When not to use
- Outliers are clearly a problem
## Hamming distance
Distance compare two bit sequences
- Hamming distance counts the number of dissimilar bits![[Screenshot 2024-01-28 at 16.14.48.jpg]]
### Implementation
```python
def hamming_distance(str_a, str_b):
    return sum(el1 != el2 for el1, el2 in zip(str_a, str_b))

```
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
### Implemetation
```python
from scipy.spatial.distance import cosine

def cosine_distance(vec_a, vec_b):
    return cosine(vec_a, vec_b)

```
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
- Is a typical data mining task  
	- Very dependent on distance  
	- Used algorithms also matters a lot 
	- Methods get into local minima  
	- Tricks to improve run-time  
	- No clear objective function

- Avoid using default settings  
- Visualize and understand the outcome 
- Apply tricks for efficiency
## K-means clustering
a good clustering is one for which the within-cluster variation(WCV) is as small as possible
The WVC for cluster k: measure the amount by which the observations within a cluster differ from each other
K-means clustering is to solve this optimisation problem: $$\underset{C_{1},...,C_{k}}{minimize}\lbrace \sum\limits^{K}_{k=1}\frac{1}{|C_{k}|}\sum\limits_{i,i'\epsilon C_{k}}\sum\limits^{p}_{j=1}(x_{ij}-x_{i'j})^{2}\rbrace$$

### How
randomly assign a number from 1 to k, to each of the observations
iterate until the cluster assignments stop changing
- for each of the k clusters, compute the cluster centroid. the  kth cluster centroid is the vector of the p feature means for the observations in the kth cluster
- assign each observation to the cluster with center closest to the observation (defined using Euclidean distance)
### Implementation
```python
from sklearn.cluster import KMeans

def kmeans_clustering(X, n_clusters=3):
    kmeans = KMeans(n_clusters=n_clusters)
    kmeans.fit(X)
    labels = kmeans.labels_
    return labels
```
### Determine the number of clusters
- based on the sum of squares within the clusters for a solution against the number of clusters
- the optimal number of clusters can be determined by the "elbow criterion"![[Screenshot 2024-01-28 at 22.08.25.jpg]]
## K-mans++
1. assign first centroid *c* to point uniformly at random
2. add *c* to *C*
3. For each datapoint *x* ε *X*
	- Compute $d(x)=min_{c\,\epsilon\, C}distance(x,c)$ 
4. assign next centroid *c* to a random point
	- with probability proportional to $d(x)^{2}$, e.g., $P(x)=\frac{d(x)^{2}}{sum\_ y\,d(x)^{2}}$
5. If less than *k* centroids are assigned, goto 3
6. Else, proceed with standard K-means


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
    - Can be determined by **visualising** the cluster solution
    - 
## CURE - clustering using representatives
- observation: non-centroid clustering is expensive
- solution: run expensive operations on small sample
- Using representatives is more commonly known as prototyping
### How
1. Learn from a sample  
	- run any expensive clustering algorithm on this batch - or batches like minibatch k-means(?)
2. Select a small set of representative points for each cluster  
	- These points should be as far apart from each other, e.g. k-means++
3. Maintain mini-clusters that will later be merged to form larger ones 
	- Key idea: merge clusters that are close to each other, use the

representatives for speed!
## BFR
For a cluster in BFR, we only require the following
1. **N** - the number of data points in the cluster
2. **SUM** - a vector containing the sums of all feature values
3. **SUMSQ** - a vector with sums of squared feature values
using these we can
1. keep track of the centroid of the cluster
2. compute the threshold for cluster membership
### How
- mean = SUM / N
- variance = $\frac{sum(x-mean)^{2}}{N}$
- = $\frac{sum(x^{2}-2mean\cdot x + mean^{2})}{n}$
- =$\frac{sum(x^{2})}{N}-\frac{2mean\cdot sum(x)}{N}+ \frac{N\cdot mean}{N}$
- $=\frac{sum(x^{2})}{N}-2mean^{2}+mean^{2}$
- $=sum\frac{x^{2}}{N}-mean$
- $=\frac{SUMSQ}{N}-(\frac{SUM}{N})^2$
- std dev. = sqrt(variance)


For each batch of points:  
- If a point is in discard set, update statistics and discard 
- For remaining points
	- Use standard clustering to obtain miniclusters  
	- Compute statistics for miniclusters, discard points 
	- Keep unclustered points in retained set

- Merge miniclusters and retained points with older miniclusters, update their statistics

# Dimensionality reduction and matrix factorisation
## Manifold learning
can capture non linear correlations between variables/features
The dataset we are working with contains a lot of "unnecessary dimensions". our data lies on a **low-dimensional manifold** (or set of manifolds) embedded in a **high-dimensional** space.
### What
Manifold learning "estimates" this **low-dimensional manifold**, typically based only on **distances** between the high-dimensional data. (Different algorithms use different distance metrics, different 'neighbourhoods' in high-dimensional space, etc. depending on their specific goals.)
![[Screenshot 2024-01-29 at 12.11.08.jpg]]
manifold learning is translation rotation and flipping invariant. 
### Disclaimer
1. In manifold learning, **we assume** that our data lies on a low-dimensional manifold.  
2. The algorithm only "sees" the **distance matrix**. It might only focus on "local" rather than "global" distances/neighbors. Low-dimensional embedding might preserve only local, but not global, distances.

Therefore, manifold methods are typically recommended **only for visualization and not downstream applications**.
## t-SNE (t-Distributed Stochastic Neighbor Embedding)
### What
based on Stochastic neighbor Embedding which has fundamental problems
- cost function is difficult to optimize
- crowding problem
*When attempting to preserve medium-range distances between data points, we also attempt to preserve the volume spanned by them. There isn't enough area/volume available in lower-dimensional spaces to reliably represent very large volumes in high-dimensional space. So when we "pull together" more distant points, we are overcrowding densely populated areas in low-dimensional space and cannot separate distinct clusters very well.*
![[Screenshot 2024-01-29 at 13.00.26.jpg]]

t-SNE proposes to solve these problems
- Cost function much easier to optimize
- Aims to both "pull together" neighboring points as much as possible, and "push apart" distant points as much as possible: *better visualization of distinct clusters*.
### How
![[Screenshot 2024-01-29 at 13.35.26.jpg]]
**cost**
Minimize the Kullback-Leibler divergence between the high dimensional similarity distribution P and the low dimensional similarity distribution Q.
![[Screenshot 2024-01-29 at 13.36.11.jpg]]
### Diff PCA SNE t-SNE
![[Screenshot 2024-01-29 at 14.36.04.jpg]]
### Analysis
**Advantages**
- Can capture **nonlinear** relationships in data
- preserves local and global structures well for visualization (i.e. well **separated clusters** in low-dimensional maps)
- effective in practice (solves optimization and crowding problems of SNE)
**Disadvantages**
- Recommended to **only use for visualization** (downstream tasks may be misled by the change in global neighborhoods or non-preservation of distances)
- Model and optimization **parameters** (e.g. 𝜎 and learning rate) need to be set by hand (cost function not convex, sensitive to initial conditions)
- computational complexity O(N2) so relatively **slow** for large datasets.

## UMAP - Uniform Manifold Approximation and Projection
UMAP is a "k-neighbour based **graph learning** algorithm".
### What
1. build a graph based on representation of the data in high dimensional space bades on **k** nearest neighbors
2. find similar graph in lower dimensions
### Comparing
![[Screenshot 2024-01-29 at 15.25.34.jpg]]

### How
The choice of nearest neighbors k defines the connectivity of the graph.  
**Larger k** → preserves more global structure, **smaller k** → preserves more local structure. 
![[Screenshot 2024-01-29 at 15.29.35.jpg]]
### Analysis
**Advantages**
- Provides well separated clusters
- Much faster than t-SNE
- Control over what information is preserved in low-D
**Disadvantages**
- **Free parameters** to be optimized (e.g. number of nearest neighbors k).  
- Global clusters preservation better than t-SNE, but distance information still lost (only **visualization**). 
- Like t-SNE non-convex optimization, sensitive to **optimization parameters** and initial conditions.
## NMF - Non-negative Matrix Factorization
### What
We factorize a matrix $A_{n\,x\,m}$ into m matrix multiplication of $B_{n\,x\,k}$ and $C_{k\,x\,m}$
$A_{n\,x\,m}$ is a non-negative matrix
We want to find non-negative matrices $B_{n\,x\,k}$ and $C_{k\,x\,m}$
```python
	def nmf(X: pd.DataFrame, n_components: int, max_iter: int=1000, tol: float=1e-3):
	
	"""
	
	Decomposes the original sparse matrix X into two matrices W and H.
	
	"""
	
	# Initialize W and H with random non-negative values
	
	W = np.random.rand(X.shape[0], n_components)
	
	H = np.random.rand(n_components, X.shape[1])
	
	old_error = np.linalg.norm(X - np.dot(W,H),ord='fro')
	
	# START ANSWER
	
	for i in range(max_iter):
		H *= np.dot(W.T,X) / (np.dot(np.dot(W.T,W),H) + 1e-9)
		
		W *= np.dot(X,H.T) / (np.dot(np.dot(W,H), H.T) + 1e-9)
		new_error = np.linalg.norm(X - np.dot(W,H),ord='fro') #Frobenius Norm
		if old_error - new_error < tol:
			break
		else:
			old_error = new_error
	# END ANSWER
	return W, H
```
# Embedding
## Word2Vec
Word2Vec is a group of models developed to produce word embeddings, which are dense vector representations of words capturing their meanings and relationships in a continuous vector space. Two primary models under Word2Vec are:

1. **Continuous Bag of Words (CBOW)**: Predicts a target word based on context words. It takes multiple context words as input and attempts to predict a single word that is most likely to appear in that context.
    
2. **Skip-Gram**: Works in reverse to CBOW. It uses a target word to predict context words. This model is particularly effective for infrequent words.
    

The algorithm works by sliding a window over text data, using the central word and surrounding context words. These words are initially represented by one-hot encoded vectors and fed into a simple neural network with a single hidden layer. The output of this network is then used to adjust the vectors to reduce the prediction error. Over many iterations and sentences, the algorithm adjusts word vectors, so words with similar meanings end up with a similar vector representation.

**Advantages**:

- Efficiently captures word meanings and semantic relationships.
- Reduces the dimensionality of text data compared to sparse representations like one-hot encoding.

**Disadvantages**:

- Requires a large amount of text data for training.
- Context-independent, meaning it generates a single embedding per word, not accounting for polysemy (words with multiple meanings).

In Python, Word2Vec can be implemented using libraries like `gensim`:

pythonCopy code

```python
from gensim.models import Word2Vec 
sentences = [["word1", "word2", "word3"], ["word4", "word5"]] 
model = Word2Vec(sentences, vector_size=100, window=5, min_count=1, workers=4) 
word_vectors = model.wv
```


This code trains a Word2Vec model on a simple dataset and gets the word vectors. The `vector_size` parameter defines the dimensionality of the word vectors.
## Node2Vec
Node2Vec is an influential algorithm for generating node embeddings in graphs. Its primary use cases include:

- **Network Analysis**: In social networks, Node2Vec can identify communities or influential individuals.
- **Recommendation Systems**: By representing users and items as nodes, Node2Vec can enhance recommendation quality.

**Advantages**:

- Captures both local and global network structures.
- Flexible in exploring diverse neighborhoods.

**Disadvantages**:

- Computationally intensive for large graphs.
- Parameter tuning (choice of p, q, walk length) can be non-trivial.

**Algorithm Explanation**:

1. **Random Walks**: Node2Vec starts by performing random walks on the graph. These walks are biased based on parameters p and q, which control the exploration-exploitation balance.
2. **Sequence Generation**: The random walks generate sequences of nodes, analogous to sentences in natural language.
3. **Optimization**: These sequences are then used to train a Skip-Gram model (from Word2Vec), optimizing to predict neighboring nodes in these sequences.

**Python Implementation**:

pythonCopy code
```python
from node2vec import Node2Vec
import networkx as nx

# Create a graph (e.g., social network graph)
graph = nx.fast_gnp_random_graph(n=100, p=0.5)

# Generate walks
node2vec = Node2Vec(graph, dimensions=64, walk_length=30, num_walks=200, workers=4)

# Train Node2Vec model
model = node2vec.fit(window=10, min_count=1, batch_words=4)

# Get vector for a node
vector = model.wv['2']  # Vector for node 2

```

This implementation uses `Node2Vec` from the `node2vec` package and `networkx` for graph handling. The example generates a random graph and creates embeddings for each node.