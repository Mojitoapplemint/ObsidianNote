[Additional Video](https://www.youtube.com/watch?v=MaY_MDdWkQw&list=PLlsmxlJgn1HJpa28yHzkBmUY-Ty71ZUGc&index=5)

# Definition
[[0. Design Pattern#Creational Design Pattern|Creational Design Pattern]] that creates the complex objects step by step
- Produces different types and representations of an object using the same construction process

# When is it used?
Used when the constructor of a class requires *many parameters*
- Sometimes we may not want to fill all the parameter

# How it works
*Extract the object construction* or creation code out of its own class and *move it to builder object*

The actual constructor should not be public
- If the builder is inner class(inner builder), then constructor should be private
- If not, then constructor should be package private(protected)
$\to$ **This forces the developer to create object only through the builder**


# Director
`some creation might share some attributes -> give it to Director`

Defines the order in which we should call the construction steps so that we can **reuse specific configurations** of the products we are building
- *Hides the detail of the product construction* from the client code

## Sharing Director
When there is another class that need the same information but have different responsibilities(creates different object), we can't share the builders, but they can share the same director
- Create a builder interface and let two builders classes implement it

# Class Diagram
![[Pasted image 20240308022033.png]]

# Example Code
```java
public class CarBuilder{
	private int id;
	private String brand;
	private String model;
	private String color;

	public CarBuilder id(int id){
		this.id=id;
	}
	
	public CarBuilder brand(String brand){
			this.brand=brand;
		}
		
	public CarBuilder model(String model){
			this.model=model;
		}
	
	public CarBuilder color(String color){
		this.color=color;
	}
	...
	// Actual Build method
	public Car build(){
		return new Car(id, brand, model, color...);
	}
}
----------------------------------------------------------
public class Car{
	private final int id;
	private final String brand;
	private final String model;
	private final String color;
	
	...
	
	// Non-public Constructor
	protected Car(int id, String brand, String model, String color...);{
	this.id = id;
	this.brand = brand;
	this.model = model;
	this.color = color;
	...
	}
}


```