# Histogram
how to make:
1. divide the range of data into intervals $B_{1},...B_{m}$ (Called bins)
2. Draw a bar of hight $h_{1}$ for bin $B_{i}$
		Approach 1: Set $h_{i}$ equal to $n_{i}=$ # data points in $B_{i}$ 
		Approach 2: Normalize the total area of the bars to 1 by setting $h_{i}$ equal to $$h_{i}=\frac{n_{i}/n}{|B_{1}|}$$
### Note
bin $B_{i}$ is an interval
- hight: $h_{i}$
- area: $|B_{i}| * h_{i}$= proportion of observations in bin i
$n$: total number of observations
$n_{i}$: number of observations in bin i
![[Screenshot 2023-04-24 at 09.46.08.jpg]]