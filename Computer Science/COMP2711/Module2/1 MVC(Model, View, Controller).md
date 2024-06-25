![[Pasted image 20240129123341.png|400]]

**Model**
- Where the *logic of the system* belongs to
- Representing data and rules govern access to and update of this data
	- It can also have business logic

**View**
- Translate the instruction to the UI
- One controller object is belong to each view object(if there is more than 2)
- Displays the data and also take input from user

**Controller**
- Acts as an interface between Model and the View parts and intercepts all incoming request
- Don't give model object to view or vise versa, but pass data to each other

# Rules of Engagement
![[Pasted image 20240129124024.png|300]]
![[Pasted image 20240129124040.png|400]]
1. Users interact with View objects
2. View objects and controller objects talk to each other
3. Different controller objects talk to each other
4. Controller objects talk to Model objects
5. No other forms of communication between objects are allowed

