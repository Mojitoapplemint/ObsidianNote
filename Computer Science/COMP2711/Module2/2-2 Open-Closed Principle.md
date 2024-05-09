Go to [[2-1 Single Responsibility Principle|Single Responsibility Principle]]
Go to [[2-3 Liskov Substitution Principle|Liskov Substitution Principle]]
Go to [[2-4 Interface Segregation Principle|Interface Segregation Principle]]
Go to [[2-5 Dependency Inversion Principle|Dependency Inversion Principle]]

[Additional Video](https://www.youtube.com/watch?v=_jDNAf3CzeY)
[Additional Reading](https://javatechonline.com/solid-principles-the-open-closed-principle/)

A class should be **open for extension**, but **closed for modification**

# Open to Extension
- Should design classes so that new functionality can be added as new requirements are generated
- New functionality should be added with minimum or no changes in the existing code
- Avoid
	1. Tight coupling
	2. If-else/switch case logic

The ways of extending a class
1. Inheriting from the class
2. Overwriting the required behaviour from the class
3. Extending certain behaviours of the class

$\to$ General Solution: *Separate the extensible behaviour through an abstract interface and turn the dependencies around*
- Make functions dependent on an abstraction(interfaces or abstract class)
- And then add new functionality by creating new classes that implement the interface

# Closed for modification
- Once you developed a class you should never modify it, except to correct bugs
- I.e. Creating a new class(or function), it shouldn't make the programmer to modify the other classes that was already exist

# Benefits
1. Easier Extensibility
2. Easier to Maintain
	- Interface's additional level of abstraction enables loose coupling
	- Each implementations are independent and don't need to share any code
3. Flexibility

# Limits
- Whenever we incorporate any change to the code as an extension, we **need to do unit testing** before and after implementing the same
