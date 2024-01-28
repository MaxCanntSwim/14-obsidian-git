point anomalies
- individual data instance is anomalous

Contextual anomalies
- an individual data instance is anomalous within a context
- requires a notion of context
- Also referred to as conditional anomalies

Collective anomalies
- A collection of related data instances is anomalous
- requires a relationship among data instances
	- Sequential data
	- spatial data
	- graph data
- individual instances within a collective anomaly are not anomalous by themselves

Time-warping
![[Screenshot 2024-01-28 at 13.49.55.jpg]]
$$(s_{1,i}-s_{2,j})^{2}$$
then find the smallest path from the top left to the bottom right, by only going right, down, or across. ![[Screenshot 2024-01-28 at 13.54.25.jpg]]

# conclusion
- 3 types of anomalies  
	- Point – point x is strange  
	- Contextual – point x is strange given set Y 
	- Collective – set Y is strange

- Modeling context  
	- Sliding windows – to model sequential context 
	- Time Warping distance – to align sequences

- Popular anomaly detection methods  
	- Classification – minimize positive space  
	- Nearest Neighbor – density or distance  
	- Spectral – remember small code (dimensions)

