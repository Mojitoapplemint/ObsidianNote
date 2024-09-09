Go to [[2-2 Open-Closed Principle|Open-Closed Principle]]
Go to [[2-3 Liskov Substitution Principle|Liskov Substitution Principle]]
Go to [[2-4 Interface Segregation Principle|Interface Segregation Principle]]
Go to [[2-5 Dependency Inversion Principle|Dependency Inversion Principle]]

[Additional Video](https://www.youtube.com/watch?v=_jDNAf3CzeY)
[Additional Reading]([SOLID Principles-The Single Responsibility Principle - JavaTechO~nline](https://javatechonline.com/solid-principles-the-single-responsibility-principle/))
Each class has only **one responsibility**, and has only **one reason to be changed**

# Responsibility
- Refers to be "a reason for change"
- Responsibility is a source of change for a user who request changes
	- Person, group, served by software
- Are tied to actors
- The actor for a responsibility is the single source of change for that responsibility

# Two values of software
- Secondary value of software is its behaviour
	- If it does for user needs, secondary value is high

# Definition
- A module should have one and only one reason to change; and only one responsibility
- Gather the things that change for the same reasons, and re separate the things that change for different reasons
