[Additional Video](https://www.youtube.com/watch?v=tSZn4wkBIu8&list=PLlsmxlJgn1HJpa28yHzkBmUY-Ty71ZUGc&index=2)

# Definition
A [[0. Design Pattern#Creational Design Pattern|creational design pattern]] for objects that restricts the instantiation of a class to one "single" instance
- Have access one object from **anywhere** in application
- Guarantee that only one instance is available

# Implementation
- Make the default constructor **private**
	- Prevent other objects from using the new operator with the Singleton class
- Create a static creation method that acts as a constructor
	- Under the hood, this method calls the private constructor to create an object and saves it in a static field
- As following calls to this method return the cached object

```java
public class alwaySingle{

	private static alwaysSingle singleton;
	private String data;

	private alwaysSingle(String data){
		this.data = data;
	}

	public static alwaysSingle getInstance(String data){
		if (singleton == null){
			singleton = new alwaysSingle(data);
		}
		return singleton;
	}
}
```

# Pros
- Ensures you have at most one instance of a class in your application
- Provides a global access point to that instance
	- Having one instance of a class makes your application more resource efficient
	- You do not have to create multiple objects every time to accomplish a task, simply grab that object anywhere and use it

