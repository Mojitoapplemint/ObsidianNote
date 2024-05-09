Q1:
1. T
2. T
3. F
4. F
5. F
6. F
7. T
8. T

Q2
A.
Stack Pointer need to be stored and restored in the Special Register after the function call is complete

B.
```
; a stored in $s0
; b sotred in $s1

lw $t0, $s0
lw $t1, $s1

slt $t9, $t0, $t1 
beq $t9, $zero, Else 

addi $t0, $t0, 1 
sw $s0, $t0 

Else: 

addi $t1, $t1, 1
sw $s1, $t1
```

C.
```c
if(s0<s1){
	s0++;
}
else{
	s1=s0+3;
}
```

Q3
A: Since the loop iterates between i=0 to 26 inclusively, it will contains 27 slot. But there are 26 alphabets, `alpha[26]` would be some other thing, not alphabet, which is not desired.

B: Code did not provide the amount of pointers is going to be stored in `rev`, thus after malloc, memory for only one pointer will be allocated in `rev`. Since size of the `rev` is not updating at each iteration as well, this will cause error from the second iteration.

C: The program needs to remove 2 arguments from the beginning, but it does only 1 argument. And $0 does not refer to the first argument, it should be $2.

Q4
The compiler determines that the concatenation would overflow bounds and produces an error at compilation time.

`strcat` does not consider the size of the destination string. Therefore, destination string will not be able to contain all element of new string and cause segmentation fault error.

Q5
Because the complier wouldn't be able to distinguish which function is the one that I want to use during the linking process. This indicates that we need to be cautious on the way we name the variable or function.
