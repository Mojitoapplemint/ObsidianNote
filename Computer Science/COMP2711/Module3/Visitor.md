[Additional Video](https://www.youtube.com/watch?v=UQP5XqMqtqQ&list=PLlsmxlJgn1HJpa28yHzkBmUY-Ty71ZUGc&index=16)
# Definition
A [[0. Design Pattern#Behavioural Design Pattern|behavioral design pattern]] that separates the algorithm or behaviors from the objects on which they operate
- Each class will be more focused on their main responsibility
- Adding new behavior is no longer open for modification
- Interchangeable by clients at runtime

## When is it used?
When you want to define new behaviour without introducing modifications to the existing object structure
- Simply adding new functionality in concrete class violates [[2-1 Single Responsibility Principle|SRP]] and [[2-2 Open-Closed Principle|OCP]]
- Thus we are using visitor instead

## Double Dispatch
`How can we know which method is correspondin to the object? Should we use tons of 'instanceof' condition?`
- Instead, delegates choosing the proper method to the object itself instead of letting the client select a method

# Class Diagram
![[Pasted image 20240308033615.png]]

`Visitor Interface`
- Declares a set of visiting methods that can take concrete elements of an object structure as arguments 

`ConcreteVisitor`
- Implement several version of the same behaviours tailored for different concrete element classes

`Element Interface & Implementations`
- Declares a method for accepting visitors
- Concrete elements much implement this method which *redirects the call to the proper visitor's method*

`Client`
- Defines a collection or some other object, and uses the visitor to invoke a certain behavior on each concrete element part of this object
# Example Code
```java
public interface Visitor{
	abstract void visitA(ElementA element);
	abstract void visitB(ElementB element);
	abstract void visitC(ElementC element);
	abstract void visitD(ElementD element);
}

public class ConcreteVisitor implements Visitor{
	public void visitA(ElementA element){
		//Do something
	}
	
	public void visitB(ElementB element){
		//Do something
	}
	
	public void visitC(ElementC element){
		//Do something
	}
	
	public void visitD(ElementD element){
		//Do something
	}
	
}
//This can be abstract class
public interface Element{
	 abstract void accept(Visitor visitor);
}

public class ElementA{
	@Override
	public void accept(Visitor visitor){
		visitor.visitA(this);
	}
}
//And for ElementB,C,D...
```