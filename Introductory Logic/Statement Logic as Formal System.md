# Extra Inference Rules
## Material Implication(ML)
$$p \to q \longleftrightarrow\neg p \lor q$$

## Transposition(TR)
$$p \to q \longleftrightarrow\neg q \to \neg p$$

## Biconditional Elimination(BEL)
$$p\longleftrightarrow q, p\therefore q$$

## Biconditional Introduction(BI)
If we can drive $q$ from supp $p$ and derive $p$ from supp $q$, then $$p\longleftrightarrow q$$
# Equivalence Rule
DN, DM, BE, TR and ML
- if and only if arguments

## Simplifying Modifications
- Equivalence Rules do not have to be applied only to whole lines
	- $(\neg p \to \neg\neg q) \to(\neg p \to q)$ by DN
- They can be applied at the same time as other rules of inference
	- Use them all in a single line

# Well-Formed Formulas(wff)
Formula is just a string of logical symbol
- If these logical symbols are ordered in a way that it can actually say something, then we say that it is well-formed

$A\to B$
- Well Formed

$A\neg B$
- Is not Well Formed

Recursive Rule
1)  Simple Statement
	- Any capital letter is wff
2) Unary Comounds
	- A wff preced by a negation symbol is wff
3) Binary Compounds
	- "LH grouper -> wff -> binary operator -> wff -> matching RH grouper" is wff
4) Only formulas that are constructible by application of the above three rules are wff

## Governing Operator
When applying recursive rules, the governing operator is whatever operators

# Theorems
Entailment ($\vdash$): one statement entails another statement is the latter follows from the former
- Basically, if an argument is valid, we can use $\vdash$ instead of $\therefore$
- $(A\&B)\vdash A$ is valid argument

A Sequent is the assertion that one statement follows from zero or more premises

Some statements are logically true or tautologous
- They are true under any interpretation
- These are called **Theorem**
- Prove by deriving it without using any premises
	- *Supposing the negation of the entire statement(RA)*


