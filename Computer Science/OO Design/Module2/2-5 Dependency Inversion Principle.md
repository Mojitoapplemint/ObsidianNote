Go to [[2-1 Single Responsibility Principle|Single Responsibility Principle]]
Go to [[2-2 Open-Closed Principle|Open-Closed Principle]]
Go to [[2-3 Liskov Substitution Principle|Liskov Substitution Principle]]
Go to [[2-4 Interface Segregation Principle|Interface Segregation Principle]]

[Additional Video](https://www.youtube.com/watch?v=_jDNAf3CzeY)
[Additional Reading]([SOLID Principles-The Dependency Inversion Principle - JavaTechOnline](https://javatechonline.com/solid-principles-the-dependency-inversion-principle/))

# Dependency Inversion Principle
- High-level modules should not depend upon low-level modules
	- *Depends on abstraction, not on concrete implementation*
- Abstraction should not depend upon details; details should depend upon abstraction

# Dependency
1. Compile Time Dependency
	- When a name defined in one module appears in the source coded of another module, then that other module has a compile time, or source code dependency on the defining module

2. Runtime Dependency
	- When the flow of control leaves one module and enters another or if during execution one module reads or writes variables in another, then those two modules have a runtime dependency
	- Exists whenever two modules interact at runtime


# Payment Example
![[Pasted image 20240214135012.png]]

