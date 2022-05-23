## Objects

Real-world objects contain state and behavior.
A software object's state is stored in fields.
A software object's behavior is exposed through methods. `Classes`
A blueprint for a software object is called a class.

## Interfaces

An interface is a reference type in Java. It is similar to class. It is a collection of abstract methods. A class implements an interface, thereby inheriting the abstract methods of the interface.

More precisely interfaces *can* have method definitions, but only of *default methods* and *static methods* but any other method type must be implemented by the class that extends it. 

- an interface is a group of related methods with empty bodies.
- If your class claims to implement an interface, all methods defined by that interface must appear in its source code before the class will successfully compile.
- Interfaces cannot be instantiated—they can only be implemented by classes or extended by other interfaces.
- To declare a class that implements an interface, you include an **implements** clause in the class declaration.
- An interface declaration can contain method signatures, default methods, static methods and constant definitions.
- An interface name can be used anywhere a type can be used


## Inheritance 

inheritance is a mechanism wherein a new class is derived from an existing class. In Java, classes may inherit or acquire the properties and methods of other classes. A class derived from another class is called a subclass, whereas the class from which a 
subclass is derived is called a superclass.

- Object-oriented programming allows classes to inherit commonly used state and behavior from other classes.
- Except for the Object class, a class has exactly one direct superclass.
- A class inherits fields and methods from all its superclasses, whether direct or indirect
- A subclass can override methods that it inherits, or it can hide fields or methods that it inherits
- You can prevent a class from being subclassed by using the final keyword in the class's declaration.
- You can prevent a method from being overridden by subclasses by declaring it as a final method.
- An abstract class can only be subclassed; it cannot be instantiated.
- An abstract class can contain abstract methods—methods that are declared but not implemented. Subclasses then provide the implementations for the abstract methods

 ## citation

 ![](https://www.tutorialspoint.com/java/java_interfaces.htm)
 Ben Mills reading repo