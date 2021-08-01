# Read: Class 06 Read: 06 - Inheritance and Interfaces

## [Java OO Tutorial](https://docs.oracle.com/javase/tutorial/java/concepts/)

- **encapsulation** is about to Hide internal data from the outside world, and accessing it only through publicly exposed methods.
- **class** is a blueprint for a software object.

### What Is Inheritance ?

- OOP allows classes to inherit commonly used state and behavior from other classes.
- In the Java programming language, each class is allowed to have one direct superclass, and each superclass has the potential for an unlimited number of subclasses.

- The `extends` keyword, Used to inherit common behavior from superclass into a subclass:

```java
class MountainBike extends Bicycle {}
```

### What Is an Interface ?

- An interface is abstract class, that is a group of related methods with empty bodies.

- If your class claims to implement an interface, all methods defined by that interface must appear in its source code before the class will successfully compile.

- To actually compile a class that uses an interface, you'll need to add the public keyword to the beginning of the implemented interface methods.

### What Is a Package ?

- A package is a namespace that organizes a set of related classes and interfaces.

- The Java platform provides an enormous class library (a set of packages) suitable for use in your own applications. This library is known as the **Application Programming Interface(API)**. Its packages represent the tasks most commonly associated with general-purpose programming. 

- The Java Platform API Specification contains the complete listing for all packages, interfaces, classes, fields, and methods supplied by the Java SE platform.

## [Java Inheritance & Interfaces Tutorial](https://docs.oracle.com/javase/tutorial/java/IandI/index.html)

### Interface

***an interface is a reference type, similar to a class, that can contain only constants, method signatures, default methods, static methods, and nested types. Method bodies exist only for default methods and static methods. Interfaces cannot be instantiated—they can only be implemented by classes or extended by other interfaces.***

- **An interface declaration consists of** modifiers, the keyword interface, the interface name, a comma-separated list of parent interfaces (if any), and the interface body.

```java
public interface GroupedInterface extends Interface1, Interface2, Interface3 {

    // constant declarations
    
    // base of natural logarithms
    double E = 2.718282;
 
    // method signatures
    void doSomething (int i, double x);
    int doSomethingElse(String s);
}
```

- The public access specifier indicates that the interface can be used by any class in any package.

- An interface can extend other interfaces, whereas a class can extend only one other class.
- The interface declaration includes a comma-separated list of all the interfaces that it extends.

- The interface body can contain abstract methods, default methods, and static methods. - An abstract method within an interface is followed by a semicolon, but no braces (it does not contain an implementation).

- All constant values defined in an interface are implicitly public, static, and final. 

- class can implement more than one interface, so the **implements** keyword is followed by a comma-separated list of the interfaces implemented by the class.

- By convention, the implements clause follows the extends clause, if there is one.

- To compare the size of similar objects, no matter what they are, the class that instantiates them should implement Relatable.
- For strings, it could be number of characters; for books, it could be number of pages; and so forth.
- If you know that a class implements Relatable, then you know that you can compare the size of the objects instantiated from that class.
- Default methods are defined with the default modifier
- static methods with the static keyword
- All abstract, default, and static methods in an interface are implicitly public, so you can omit the public modifier.
- All constant values defined in an interface are implicitly public, static, and final. Once again, you can omit these modifiers.

- If you define a reference variable whose type is an interface, any object you assign to it must be an instance of a class that implements the interface.

***An interface declaration can contain method signatures, default methods, static methods and constant definitions. The only methods that have implementations are default and static methods.***

***A class that implements an interface must implement all the methods declared in the interface.***

***An interface name can be used anywhere a type can be used.***

### Inheritance

- Classes can have fields whereas interfaces cannot.
- One reason why the Java programming language does not permit you to extend more than one class is to avoid the issues of multiple inheritance of state, which is the ability to inherit fields from multiple classes.

- The Java programming language supports **multiple inheritance** of type (The ability of a class to implement more than one interface).

- An object can have multiple types: the type of its own class and the types of all the interfaces that the class implements.

- **An instance method** is a method that belongs to instances of a class, not to the class itself.
- Overriding is a feature that allows a subclass to provide a specific implementation of a method that is already provided by one of its super-classes or parent classes.

- The inherited fields can be used directly, just like any other fields.
- You can declare a field in the subclass with the same name as the one in the superclass, thus hiding it (not recommended).
- You can declare new fields in the subclass that are not in the superclass.
- The inherited methods can be used directly as they are.
- You can write a new instance method in the subclass that has the same signature as the one in the superclass, thus overriding it.
- You can write a new static method in the subclass that has the same signature as the one in the superclass, thus hiding it.
- You can declare new methods in the subclass that are not in the superclass.
- You can write a subclass constructor that invokes the constructor of the superclass, either implicitly or by using the keyword super.
- A subclass does not inherit the private members of its parent class.
  
- A nested class has access to all the private members of its enclosing class—both fields and methods. Therefore, a public or protected nested class inherited by a subclass has indirect access to all of the private members of the superclass.

- ***Casting*** shows the use of an object of one type in place of another type, among the objects permitted by inheritance and implementations.
- You can make a logical test as to the type of a particular object using the instanceof operator. This can save you from a runtime error owing to an improper cast
- You can prevent a class from being subclassed by using the final keyword in the class's declaration.
- you can prevent a method from being overridden by subclasses by declaring it as a final method.
- An abstract class can only be subclassed; it cannot be instantiated.
  