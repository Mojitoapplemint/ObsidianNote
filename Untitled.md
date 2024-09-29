1. This is an insertion sort that takes an array $A$ and the length of the array, $n$ as inputs, then sort the array $A$

2. The outer loop iterates in terms of index of $A$, from 2 to $n$, then assign a value at that nidesx to a variable called key

3. During each step, from the leftside of key, elements are pushed to the right until either it reaches the first element or found the element that is smaller than the key

4. If the inner loop terminates, 

1. $i$ value is assigned from 2 to $n$ and the inner loops keep reassigning $j$ value from $i-1$ to 1 and check whether $j$ reached 0 or $A[j]$ is bigger than the key

2. If $A[j]$ is bigger than the key, the inner loop terminates, otherwise, it is pushed to the right and $j$ is decreased by 1

3. When the inner loop terminates, key value is assigned to $A[j+1]$ and this cycle repeats until $i$ reaches $n$ so that the array is sorted