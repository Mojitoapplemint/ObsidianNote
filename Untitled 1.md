# Close Subset
Want to generalize sets like $[0,1]$
- One property this set has is if $\{ a_{n} \}$ is a sequence entirely in $[0,1]$, and it converges to $L$, then $L\in[0,1]$
- This is not true for, for example, $((0,1), a_{n}=\frac{1}{n})$ is always in the set but what it converges is not

## Close Subset
Suppose $(X,d)$ is a metric space, $A\subseteq X$, $A$ is said to be closed in $(X,d)$ if for any sequence $\{ a_{n} \}$ such that $\forall \text{ }n\in\mathbb{N}$, $a_{n}\in A$, and $\{ a_{n} \}$ converges to $L$, then $L\in A$ also

**Ex)**
$[0,1]$ is closed in $(\mathbb{R}, \text{usual metric})$

$\emptyset$ is closed in any metric space

In an arbitrary metric space $(X,d)$, is $X$ closed?
- Yes, $\{ a_{n} \}$ converges to $L$ in $(X,d)$, the  $L$ by definition must be in $X$
- So, $X$ is closed

For any set $X$, if $d$ is the discrete metric for any $A\subseteq X$, $A$ is closed in $(X,d)$
- Suppose $\{ a_{n} \}$ is a sequence in $A$ converges to $L$ in $X$, by ass question, $\{ a_{n} \}$ must be eventually constant, and so converges to one of the values in the sequence, which are all by definition in $A$, so $L$ is in $A$, so $A$ is closed

**Exercise)**
Show any finite non-empty subset of $\mathbb{R}$ is closed but not open $(\mathbb{R}, \text{usual metric})$

## Prop 70
If $(X,d)$ is a metric space, $A\subseteq X$, then $A$ is closed in $(X,d)$ iff $X\text{ \\ }A=\{ x\in X:x\not\in A \}$ is open in $(X,d)$

**Proof)**
i) Forward Direction: by contrapositive
- If $X\text{\\}A$ is not open, then $A$ is not closed
- Then there is some point $x\in X\text{\\}A$ such that for all $\epsilon>0$, $B_{\epsilon}(x)\not\subseteq X\text{\\}A$

If we let $\epsilon=1$, there is some $a_{1}\in A$ such that $a_{1}\in B_{1}(x)$
If we let $\epsilon=2$, there is some $a_{2}\in A$ such that $a_{2}\in B_{1}(x)$
	$\vdots$
Generally, for any $n\in \mathbb{N}$, there is an $a_{n}\in A$ with $a_{n}\in B_{\frac{1}{n}}(x)$

Then, claim that $\{ a_{n} \}$ conv to $X$. Given any $\epsilon>0$, let $K=\frac{1}{\epsilon}$, sps $n>K$. then $\frac{1}{n}<\epsilon$
- Then, $d(a_{n}, x)<\frac{1}{n}$ since $x\in B_{\frac{1}{n}}(x)$
- $\therefore d(a_{n}, x)<\epsilon$
- So $\{ a_{n} \}$ is all in $A$, yet converges to $x\not\in A$. So, $A$ is not closed