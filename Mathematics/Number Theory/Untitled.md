# Theorem 4.1 Complete System of Residue
A complete system of residues modulo $m$ is a set of integers such that every integer is congruent modulo $m$ to exactly one integer in the set

**Example)** $\{0,1,2,3\}$ is a complete system of resudues modulo 4

## Least Nonnegative resudues mod $m$
- $\{1,2,\dots m-1\}$

# Theorem 4.2 Linear Congruence
A Congruence of the form 
$$ax\equiv b(\text{mod m})$$
When $x$ is unknown integer, is called a linear congruence

## If $x_{0}$ is a solution and $x_{0}\equiv x_{1}(\text{mod m})$, then $x_{1}$ is also solution
Suppose $x_{0}$ is a solution
$$ax_{0}\equiv b(\text{mod m})$$
- $m|(ax_{0}-b) \implies mk=ax_{0}-b$

From $x_{1}\equiv x_{0} (\text{mod m})$, $m|(x_{1}-x_{0}) \implies x_{0}=x_{1}-ml$

Then, $mk=a(x_{1}-ml)-b$
- $m(k+al)=ax_{1}-b$
- $\implies ax_{1}\equiv b(\text{mod m})$

