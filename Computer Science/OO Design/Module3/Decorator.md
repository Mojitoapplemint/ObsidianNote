# Definition
A [[0. Design Pattern#Structural Design Pattern|structural design pattern]] that let developer attach new behaviors to an object by placing this object inside a special wrapper that contains these behaviors

# Implementation
- Create an interface
- Create concrete classes that implement the same interface as the abstract class
- Create an abstract decorator class that implements the same interface as the above
- Create a concrete decorator class that extends the abstract decorator class mentioned above
- Decorate interface objects with the concrete decorator class generated earlier

# Structure
![[Pasted image 20240308050445.png]]
`Component`
- Declares common behaviors for both *wrappers and wrapped object*
`Concrete Component`
- Wrapped Class
- Defines basic behavior, which can be altered by decorators
`BaseDecorator`
- References the wrapped object via interface so it can reference both the concrete component and its decorator
`ConcreteDecorator`
- Override the methods of the `BaseDecorator`
- But still make use of it either before or after calling parent method
`Client`
- Wraps components in layers of decorators
- Must work via the component interface

# Example Code
```java
public interface Icecream {
  public String makeIcecream();

public class SimpleIcecream implements Icecream {

    @Override
    public String makeIcecream() {
        return "Base Icecream";
    }
}

abstract class IcecreamDecorator implements Icecream {

    protected Icecream specialIcecream;

    public IcecreamDecorator(Icecream specialIcecream) {
        this.specialIcecream = specialIcecream;
    }

    public String makeIcecream() {
        return specialIcecream.makeIcecream();
    }
}

public class NuttyDecorator extends IcecreamDecorator {

    public NuttyDecorator(Icecream specialIcecream) {
        super(specialIcecream);
    }

    public String makeIcecream() {
        return specialIcecream.makeIcecream() + addNuts();
    }

    private String addNuts() {
        return " + crunchy nuts";
    }
}

public class HoneyDecorator extends IcecreamDecorator {

    public HoneyDecorator(Icecream specialIcecream) {
        super(specialIcecream);
    }

    public String makeIcecream() {
        return specialIcecream.makeIcecream() + addHoney();
    }

    private String addHoney() {
        return " + sweet honey";
    }
}
-----------------------------------------------------------
public class TestDecorator {

    public static void main(String args[]) {
        Icecream icecream = new HoneyDecorator(new NuttyDecorator(new BasicIcecream()));
        System.out.println(icecream.makeIcecream());
    }
}

//Output: Basic Icecream + crunchy nuts + sweet honey
```