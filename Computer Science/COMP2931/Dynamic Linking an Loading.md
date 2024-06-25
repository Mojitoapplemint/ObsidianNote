# Loading
Process of setting up a program to run
- OS's responsibility
- Load need to
	- Create an address space
	- Load text and data into new address space
	- Copy arguments to the main function to the stack
	- Initialize registers and program counter

After loading, we can link to data
- Put each shared library to memory
- Add symbols to the Global Offset Table(GOT)

Then, we can set the PC to the beginning of the program and start running it

# Dynamic Linking: Calling a Function
- Save PC
- Determine the new value for PC
	- Just follow the normal procedure if it's local function
	- If the function has been called before, jump to the permanent value in the GOT
	- Jump to the Procedure Locator Table, which includes instructions for determining the correct jump address
	- Determine the correct address to jump to
	- Save the address to the GOT
	- Jump to the new address without changing saved return address

Why?
- If we need to modify code to include offsets, we can't share the same instructions between multiple processes
- Adding indirection allows the use of Position Independent Code(PIC) no need to set offsets in text
- Therefore we can share one copy of the text between multiple processes

Dynamic Linking and shared objects have additional overhead, but allow flexibility, or sometimes save memory

# Neat Features of C: Function Pointers
Function pointers allow references to functions to be passed as arguments, stored, etc

How do we define a function that takes a function pointer as an argument?
- `void name(int<ReturnType> (*comp_fn"FunctionName")(int, int)<ArgumentType>, int *data)`
Call a function
- `(*comp_fn"FunctionName")(x,y)`
Getting a pointer to a specific function
- `&fn_name`

