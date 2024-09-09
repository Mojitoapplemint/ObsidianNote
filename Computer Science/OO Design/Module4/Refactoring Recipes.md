# Extract Method
Code Smell: Long Function, Duplicate Code, Divergent Change
Method that is too long, code that *needs a comment to understand its purpose*
- Move duplicated code to a separate new method (or function) and replace the old code with a call to the method.
- Short and well-named methods
- If we can't extract the method due to local variable, Split Temp Variable, or eliminate is by [[Refactoring Recipes#Replace Temp With Query|Replace Temp with Query]]
- 
## Example
```java
// BEFORE
void printOwing() {
  printBanner();

  // Print details.
  System.out.println("name: " + name);
  System.out.println("amount: " + getOutstanding());
}

// AFTER
void printOwing() {
  printBanner();
  printDetails(getOutstanding());
}

void printDetails(double outstanding) {
  System.out.println("name: " + name);
  System.out.println("amount: " + outstanding);
}
```

# Move Method
- Create a new method in the class that uses the method the most, then move code from the old method to there. 
- Turn the code of the original method into a reference to the new method in the other class or else remove it entirely.

# Replace Conditional with Polymorphism
Code Smell: Long Function, Repeated Switches

Problem: Have conditional that performs various actions depending on object type or properties
- Create subclasses matching the branches of the conditional. In them, create a shared method and move code from the corresponding branch of the conditional to it. Then replace the conditional with the relevant method call. The result is that the proper implementation will be attained via polymorphism depending on the object class.
- If there is no pre-made polymorphism, create it using [[Refactoring Recipes#Replace Type Code with Subclasses|Replace Type Code with Subclasses]] or [[Refactoring Recipes#Replace Type Code with State/Strategy|Replace Type Code with State/Strategy]]
```java
//BEFORE
class Bird {
  // ...
  double getSpeed() {
    switch (type) {
      case EUROPEAN:
        return getBaseSpeed();
      case AFRICAN:
        return getBaseSpeed() - getLoadFactor() * numberOfCoconuts;
      case NORWEGIAN_BLUE:
        return (isNailed) ? 0 : getBaseSpeed(voltage);
    }
    throw new RuntimeException("Should be unreachable");
  }
}

//AFTER
abstract class Bird {
  // ...
  abstract double getSpeed();
}

class European extends Bird {
  double getSpeed() {
    return getBaseSpeed();
  }
}
class African extends Bird {
  double getSpeed() {
    return getBaseSpeed() - getLoadFactor() * numberOfCoconuts;
  }
}
class NorwegianBlue extends Bird {
  double getSpeed() {
    return (isNailed) ? 0 : getBaseSpeed(voltage);
  }
}

// Somewhere in client code
speed = bird.getSpeed();
```

## Replace Type Code with Subclasses
Problem: You have a coded type that directly affects program behavior (values of this field trigger various code in conditionals)
- Create subclasses for each value of the coded type. Then **extract the relevant behaviors** from the original class to these subclasses. Replace the control flow code with polymorphism.

### Example
Before
![[Pasted image 20240331232202.png]]

After
![[Pasted image 20240331232220.png|300]]

## Replace Type Code with State/Strategy
Problem: You have a coded type that affects behavior but you *can't use subclasses* to get rid of it.
- Replace type code with a state object. If it's necessary to replace a field value with type code, another state object is "plugged in"

### Example
Before
![[Pasted image 20240331232424.png|150]]

After
![[Pasted image 20240331232454.png|300]]


# Replace Temp With Query
Code Smell: Long Function

Problem: You place the result of an expression in a local variable for later use in your code
- Move the entire expression to a separate method and return the result from it. 
- Query the method instead of using a variable. Incorporate the new method in other methods, if necessary
- **Often vital step** before [[Refactoring Recipes#Extract Method|Extract Method]]
- *May split the variable and methods first, if they are responsible more than one thing*

## Example
```java
//BEFORE
double calculateTotal() {
  double basePrice = quantity * itemPrice;
  if (basePrice > 1000) {
    return basePrice * 0.95;
  }
  else {
    return basePrice * 0.98;
  }
}

//AFTER
double calculateTotal() {
  if (basePrice() > 1000) {
    return basePrice() * 0.95;
  }
  else {
    return basePrice() * 0.98;
  }
}
double basePrice() {
  return quantity * itemPrice;
}
```

# Change Function Declaration
- Rename Function
- Rename Method
- Add Parameter
- Remove Parameter
- Change Signature

# Slide Statement
- i.e. Consolidate Duplicate Conditional Fragments
- Move duplicated code outside of the conditional
## Example
```java
//BEFORE
if (isSpecialDeal()) {
  total = price * 0.95;
  send();
}
else {
  total = price * 0.98;
  send();
}

//AFTER
if (isSpecialDeal()) {
  total = price * 0.95;
}
else {
  total = price * 0.98;
}
send();
```




# Pull Up Method
Your subclasses have methods that perform similar work
- Make the methods identical and then move them to the relevant superclass
## Example
Before
![[Pasted image 20240330153509.png|300]]
After
![[Pasted image 20240330153529.png|300]]




# Encapsulate Variable
- Make the field(variable) private and create getter & setter method to it

# Self Encapsulate Field
- Make the field(variable) private and create getter & setter method to it, but let them private
