1. This is an insertion sort that takes an array $A$ and the length of the array, $n$ as inputs, then sort the array $A$

2. The outer loop iterates in terms of index of $A$, from 2 to $n$, then assign a value at that nidesx to a variable called key

3. During each step, from the leftside of key, elements are pushed to the right until either it reaches the first element or found the element that is smaller than the key

4. If the inner loop terminates, 

1.  $i$ value is assigned from 2 to $n$, then assign a value at that index to a variable called key.

2. $j$ is initialized as $i-1$ and while it keeps decreasing by 1, the inner loops checks whether either $A[j]$ is bigger than the key or $j$ reached 0

3. The inner loops terminate if one of the condition satisfied, then key value is assigned to $A[j+1]$ and this cycle repeats until $i$ reaches $n$ so that the array is sorted