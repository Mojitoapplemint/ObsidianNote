[Additional Video](https://www.youtube.com/watch?v=EdFq_JIThqM&list=PLlsmxlJgn1HJpa28yHzkBmUY-Ty71ZUGc&index=3)

# Factory
A [[0. Design Pattern#Creational Design Pattern|Creational Design Pattern]] loosens the coupling of a given code by separating the product's construction code from the code that uses this product
- Encapsulate the responsibility of creating the object to the factory object $\to$ Resolve [[2-1 Single Responsibility Principle|SRP]]
- But still it is [[2-2 Open-Closed Principle|open for modification]]

# Factory Method Pattern
Factory Method handles objects creation and encapsulates it in **subclass**
- This decouples the client code in the superclass from the object creation code in the subclass

In Other Words...

Factory Method defines an interface for creating an object, but lets subclasses decide which class to instantiate
- Heavily relies on inheritance

## How it works?
- Make the client class abstract/interface *to make the creation method abstract*
	- This is called Factory Method
- Implement creation method in each subclass

## When is it used?
- If you have **no idea of the exact types of the objects** your code will work with

# Class Diagram
![[Pasted image 20240308031110.png]]

