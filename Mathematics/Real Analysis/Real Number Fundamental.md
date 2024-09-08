# Binary Operations
Binary Operation on a set $A$
- A function: $A\times A \rightarrow A$
- Takes two elements from $A$ as inputs and we can get something from $A$ as output

# Axioms for $\mathbb{R}$
Axiom
- Statement or proposition which is regarded as being established, accepted, or self-evidently true
- Fact that we don't prove but consider as true

## Associativity of Addition
For all $x,y,z\in\mathbb{R}$
$$x+(y+z)=$$


# Further Rules can be proved
## Lemma 1. For any $x,y,z\in\mathbb{R}$, if $x+y=x+z$, then $y=z$
Assume $x+y=x+z$

By $R.4$, there is a $-x\in\mathbb{R}$. Add it to both sides
- $-x+(x+y)=-x+(x+z)$
Then, by Associativity of Addition ($R.1$), 
- $(-x+x)+y=(-x+x)+z$
By Communitativity of addition ($R.2$)
- $(x+(-x))+y=(x+(-x))+z$
By Inverse of Addition ($R.4$)
- $0+y=0+z$
By Communitativity of addition ($R.2$)
- $y+0=z+0$
By Unitiality of Addition ($R.3$)
- $y=z$

### Claim: $1+1\neq 1$
If it was true, then $1+1=1$
Then, $1+1=1+0$ by $R.3$
Then, $1=0$ by lemma 1
$\rightarrow$ This contradicts $R.7$
## Lemma 2. For any $x\in\mathbb{R}, x\cdot {0}=0$
Consider $x\cdot {0}$
	$= x \cdot (0+0)$ by $R.3$
	$= x\cdot 0+x\cdot 0$ by $R.9$

So, $x\cdot 0= x\cdot 0 + x\cdot 0$ 
	$x\cdot 0+0 = x\cdot 0+x\cdot 0$ by $R.3$
	$0=x\cdot 0$ by Lemma 1

