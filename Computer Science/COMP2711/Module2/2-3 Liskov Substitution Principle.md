Go to [[2-1 Single Responsibility Principle|Single Responsibility Principle]]
Go to [[2-2 Open-Closed Principle|Open-Closed Principle]]
Go to [[2-4 Interface Segregation Principle|Interface Segregation Principle]]
Go to [[2-5 Dependency Inversion Principle|Dependency Inversion Principle]]

[Additional Video](https://www.youtube.com/watch?v=_jDNAf3CzeY)
[Additional Reading]([SOLID Principles-The Liskov Substitution Principle - JavaTechOnline](https://javatechonline.com/solid-principles-the-liskov-substitution-principle/))
# Definition
- Subtype must be substitutable for their base types
	- Subtype must behave like its supertype
	- Must adhere to the behavioural specification of the supertype
- Need to ask
	- Does method in base type maintain and have actual purpose in the subtype?

Abusing LSP increases the difficulty of debugging
- Hard to recognize which method is used

# Spotting LSP Violation
- Used to violate Open-Closed Principle

## Signature rule
- Overridden subtype method argument types can be identical or wider
- return type of the subtype method can be narrow or identical with the supertype
- Can throw fewer exception

## Properties rule
- Class invariant is an assertion concerning object properties that must be true for all valid states of the objects
- Subclass method shouldn't allow state changes that the base case didn't allow

## Methods rule
- Precondition should be satisfied before method execution
	- Subtype can be weaken, but cannot strengthen, the precondition for a method it overrides
- Post condition is a condition that should be satisfied after method execution
	- The subtype can strengthen, but not weaken the post condition 

## Representative Rule
- 

# Type of Violation
## Undefined Behaviour
- 

## Refused Bequest
- Subclass inherit unnecessary methods and data of their parent
- Let two classes are sibling and create another abstracts that contains only something in common

1. When subtype contain degenerate function
2. Derive method that does nothing but throw an exception
3. If we have to check the instance when we don't know the specific type of instance
	- But still might violate [[2-2 Open-Closed Principle|OCP]]
4. 

# Code Smell
- A subtype throws an exception for a behaviour it can't fulfill
- A subtype provides no implementation for a behaviour it can't fulfill
- 


# Delegation
- One class hands off the task of doing something to another class
- 

