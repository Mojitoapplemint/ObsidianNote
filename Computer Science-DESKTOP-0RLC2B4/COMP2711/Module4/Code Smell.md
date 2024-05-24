# Long Function

**Recipes**
- [[Refactoring Recipes#Extract Function|Extract Function]]
- [[Refactoring Recipes#Replace Temp With Query|Replace Temp with Query]]
- Introduce Parameter Object
- Preserve Whole Object
- Replace Function with Command
- Decompose Conditional
- [[Refactoring Recipes#Replace Conditional with Polymorphism|Replace Conditional with Polymorphism]]

# Repeated Switches
The same conditional switching logic
**Recipes**
- [[Refactoring Recipes#Replace Conditional with Polymorphism|Replace Conditional with Polymorphism]]

# Duplicated Code
Same code structure exists in more than one place

**Recipes**
- [[Refactoring Recipes#Extract Function|Extract Function]]
- [[Refactoring Recipes#Slide Statement|Slide Statement]]: When codes are similar but not quite identical
- [[Refactoring Recipes#Pull Up Method|Pull Up Method]]: Duplicate fragments are in subclass

# Mysterious Name
Code need to be mundane and clear
- Good Name: functions, modules, variables, classes

**Recipes**
- [[Refactoring Recipes#Change Function Declaration|Change Function Declaration]]
- Rename Variable
- Rename Field

# Primitive Obsession


# Long Parameter List

**Recipes**
- Replace Parameter with Query
- Preserve Whole Object
- Introduce Parameter Object
- Remove Flag Argument
- combine Functions into class

# Global Data
The problem with global data is that it can be modified from anywhere in the code base, and there's no mechanism to discover which bit of code touched it; it's very hard to find out where the errant bit of program is

**Recipes**
- [[Refactoring Recipes#Encapsulate Variable|Encapsulate Variable]]

# Data Class
Classes that have instance, getting and setting methods, and nothing else

**Recipes**
- [[Refactoring Recipes#Encapsulate Variable|Encapsulate Variable]]

If there is better location
- [[Refactoring Recipes#Move Method|Move Method]]
- [[Refactoring Recipes#Extract Method|Extract Method]]



# Mutable Data
Bug is hard to detect when the data is mutable

**Recipes**
- [[Refactoring Recipes#Encapsulate Variable|Encapsulate Variable]]
- Split Variable
- [[Refactoring Recipes#Slide Statement|Slide Statement]]
- [[Refactoring Recipes#Extract Function|Extract Function]]
- Separate Query from Modifier
- Remove Setting Method
- Replace Derived Variable with Query
- Combine Functions into Class
- Combine Functions into Transform
- Change Reference to Value

# Divergent Change
When one module is often changed in different ways for different reasons
- Moving different context to separate module

**Recipes**
- Split Phase
- Move Function
- [[Refactoring Recipes#Extract Method|]]
- Extract Class

# Shotgun Surgery
Every time you make a change, you have to make a lot of little edits to a lot of different classes



# Feature Envy

# Data Clumps

# Lazy Element

# Speculative Generality

# Temporary Field

# Message Chains

# Middle Man

# Insider Trading

# Large Class

# Alternative Classes with Different Interface

# Refused Bequest

# Comments
  
