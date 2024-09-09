# Q1

a)This command is getting an access to the value that the “Pointer” &x is pointing. In other words, there is another value that the pointer &x is pointing, and `*\$` is getting an access that value.

b)Assuming that “a” is an array, then yes. The pointer `*(a+1)` is pointing the value of index number 1 in array, which is a[1].

c)There shouldn’t be space “ ” between letters, thus it should be “i=0”

d)I would use C rather than bash because of the mathematical flexibility in C is significantly stronger than bash. In C, there is preprocessor “math.h” that offers various mathematical functions, including trigonometry, logarithm, etc. On the other hand, pure bash script doesn’t support floating point numbers, thus complicate mathematical calculations would be hard to operated in bash. Therefore, considering physics simulations require a lot of mathematical operations, C would be more suitable than bash

# Q2

A)
Answer: `^\$`

Since $ means the end of the line in regular expression, to use its textual value, we need to add ![](file:///C:/Users/woong/AppData/Local/Temp/msohtmlclip1/01/clip_image004.png) to indicate that the dollar sign is for textual value, not its functionality as regular expression. Then, we need to force the dollar sign to appear at the front, thus ^ comes in front of the textual value of $. Therefore, the answer is the above.

B)
Answer: `^\$[0-9]*[IOo]+`

Since we need to recognize the letter “I”, “O”, “o”, let the regular expression detect whether either one of them appear at least once by `[IOo]+` . Since those letters do not necessarily appear right after “$,” thus I put regex `[0-9]*` to make sure that the command detect the replacement whether there are some numbers before the replacement or not.

C)
Answer:
```Shell
//let $input is the nunber that is being filtered

input=$(sed s/'-0'/'0'/ <<< $input)

if [ $(grep -Ec '\.[0-9]*e' <<< $input ) -eq 1 ]
then
	//Nothing happen
else
	input=$(sed s/'\.[0-9]*'/""/ <<<$input)
fi
```

# Q3
A)
```Bash
find .. | chmod u+x $(grep '.sh$')
```

B)
```Bash
find ~/TestDir | grep '\.[ch]$' | grep -r "#define"
```

C)
```bash
find . | grep -c '\.[ch]$'
```

D)
```shell
find . | cat $(grep '\.txt$') >> alltext.out
```
# Q5

B) In general, implementation through bash was simpler than C. Since array in C is pointer, I was required to be extra cautious because of dereferencing; accessing the element in array/list was way simpler in bash. On the other hand, bash script has very strict structure and C is relatively similar to java, writing basic code was simpler in C than bash.Q1
