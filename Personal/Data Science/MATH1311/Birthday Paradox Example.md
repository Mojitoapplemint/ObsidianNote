
- If there are 23 people, there will be 50% of chance that two people shares birthday
- If there are 40 people, there will be 89% of chance that two people shares birthday
	- It is called paradox because required amount people seems too low
	- This happen because we think as individual point of view

1. If there are $N$ people and each of them can pick a birthday
	- Permutation with repetition: $365^{N}$
2. How many groups of size $k$ can we have?: 
	- $N$ people, how many subgroups of $k$ people we can choose: $_{N}C_{k}$

- If we have $N$ people has unique birthday, number of case would be
	- $_{365}P_{N}$
- But what if there are 366 people has unique birthday
	- Impossible: Pigeon Hole Principle

1) If $k=1$
	- impossible: $P(1)=0$
2) If $k=2$
	- First person has 365 choices, second person has 1(follow first)
	- And then other people have to choose unique choice
	- And this can happen to any two people 
$$365\cdot (_{364}P_{N-2})\cdot (_{N}C_{2})$$
3) If $k=3$
- First person has 365 choices, second and third people has 1
- And then other people have to choose unique choice
- And this can happen to any three people 
$$365\cdot (_{364}P_{N-3})\cdot (_{N}C_{3})$$
In general,
$$P(k)=\frac{365\cdot_{364}P_{N-k} \cdot_{N}C_{k}}{365^{N}}$$