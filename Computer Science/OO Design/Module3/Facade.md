[Additional Video](https://www.youtube.com/watch?v=xWk6jvqyhAQ&list=PLlsmxlJgn1HJpa28yHzkBmUY-Ty71ZUGc&index=22)
`We need a centralized place to pull all of the logic inside it, to center it , and to restrict diret access to the inner workings of the library`

# Definition
A [[0. Design Pattern#Structural Design Pattern| structural design pattern]] that provides a simplified interface to a set of interfaces in the subsystem to make it easier to use
- Client interacts with the facade and the facade interface is responsible for calling function of the existing subsystem

# When should we use?
- When I need to integrate your application with a sophisticated library that has dozens of features, but you just need a tiny bit its functionality

# Structure
![[Pasted image 20240308052905.png]]
`Facade` 
- Provides convenient access to a particular part of the subsystem's functionality. 
- Knows where to direct the client's request and how to operate all the moving parts
`Additional Facade`
- Can be created to prevent polluting a single facade with unrelated features that might make it yet another complex structure
- Can be used by both clients and other facades
`Complex Subsystem`
- Consists dozens of various objects
- Subsystem classes aren't aware of facade's existence, they operate within the system and work with each other directly
`Client`
- Uses facade instead of calling the subsystem object directly