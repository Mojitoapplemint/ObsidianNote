# Definition
A [[0. Design Pattern#Structural Design Pattern|structural design pattern]] that lets you compose objects into tree structures and then work with these structures as if they were individual objects

Passing the instruction of task to its children is the responsibility of composite

# Component and Composite
Component
- Provides a layer of abstraction for all classes in the hierarchy
Composite
- Has a collection of components that extend the component class

Both Component and Composite *share a common interface*
- This allows the client to treat individual objects and composition uniformly

# Pros
- Easier to add new kinds of components to an already-built structure
- Makes the client code simple
	- Caller doesn't need to know whether the component is simple or complex
	- It can only take that component and do the intended task

# Structure
![[Pasted image 20240308041846.png]]
1. The `Component Interface` describes operations that are common to both simple and complex elements of the tree
2. The `Leaf` is basic element of a tree that doesn't have sub-element
3. The `Composite` is an element that has sub elements: Leaves or other containers
	- Doesn't know the concrete classes of its children. It works with all sub-elements only via the component interface
4. The `Client` works with all elements through the component interface
	- As a result, the client can work in the same way with both simple and complex elements of the tree