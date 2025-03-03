---
dg-publish: true
---
#Code

```python
import numpy as np
import matplotlib.pyplot as plt

# create a set of Bernouli random matrices

num_sims = 100
N = 500
sims = []


for i in range(num_sims):
	matrix_list = []
	eigenvalues = []
	for i in range(N):
		
		b1 = np.random.choice([0, 1])
		b2 = np.random.choice([0, 1])
		matrix = np.array([[b1, b2], [b2, b1]])
		matrix_list.append(matrix)
	
	matrix_list = np.array(matrix_list)
	sims.append(matrix_list)

sims = np.array(sims)

```

```python
# then find the eigenvalues for each item in the list

sim_evalues = []

for sim in sims:
	eigenvalues_list = np.array([np.linalg.eigvals(matrix) for matrix in sim])
#
	sim_evalues.append(eigenvalues_list)

sim_evalues = np.array(sim_evalues)
print(sim_evalues.shape) # should be (num_sims, N, 2)
```

```python
# we will define some region delta to see if we have eigenvalues in here
delta = 1
# in the example, the first delta is just any eigenvalue that isn't 1

probs = []

for evalues in sim_evalues:
	count = 0 # number of matrices with eigenvalues satisfying delta
	for e in evalues:
		
		degenerate = e[0] == e[1]
		# we only count evalue once if there is degeneracy
			
		if (e[0] != delta) and (e[1] != delta):
			# we only want cases with 1 evalue not equal to delta
			if degenerate:
				# hence then this is only 1 eigenvalue in the set of eigenvalues
				count += 1
			continue
		elif (e[0] == delta) and (e[1] == delta):
			# hence no eigs satisy delta - not right
			continue
		else: 
			# else only 1 satisfies
			count += 1
		
	P_cf_is_1 = count / N
	probs.append(P_cf_is_1)
		
probs = np.array(probs)

```

```python
#plot results

mean = np.average(probs)

plt.hist(probs, bins=10, edgecolor='black', alpha=0.7)
plt.axvline(mean, color="black", label=f"Mean: {mean:.3f}")
plt.xlabel("Probability") 
plt.ylabel("Frequency") 
plt.title(rf"${delta} \in\not \Delta$") 
plt.legend()
plt.show()
```