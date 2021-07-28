# Read: Class 04 Read: 04 - OOP

## [Object-Oriented Programming Concepts](https://docs.oracle.com/javase/tutorial/java/concepts/)

### What Is an Object?

***An object is a software bundle of related state and behavior. Software objects are often used to model the real-world objects that you find in everyday life.***

- An object stores its state in fields (variables in some programming languages) and exposes its behavior through methods (functions in some programming languages).
- Hiding internal state and requiring all interaction to be performed through an object's methods is known as data encapsulation
- Bundling code into individual software objects provides a number of benefits, including:
   - Modularity: The source code for an object can be written and maintained independently of the source code for other objects
   - Information-hiding: By interacting only with an object's methods, the details of its internal implementation remain hidden from the outside world.
   - Code re-use: If an object already exists (perhaps written by another software developer), you can use that object in your program
   - Pluggability and debugging ease: If a particular object turns out to be problematic, you can simply remove it from your application and plug in a different object as its replacement

![Object](https://docs.oracle.com/javase/tutorial/figures/java/concepts-object.gif)

### What Is a Class?

***A class is a blueprint or prototype from which objects are created.***

- classes defined in the following way:

```java
class MyClass {
    // field, constructor, and 
    // method declarations
}
```

- The class body (the area between the braces) contains all the code that provides for the life cycle of the objects created from the class: constructors for initializing new objects, declarations for the fields that provide the state of the class and its objects, and methods to implement the behavior of the class and its objects.

- You can provide more information about the class, such as the name of its superclass, whether it implements any interfaces, and so on, at the start of the class declaration. For example: 

```java
class SubClass extends MySuperClass implements YourInterface {
    // field, constructor, and
    // method declarations
}
```

- In general, class declarations can include these components, in order:

    1. Modifiers such as public, private, and a number of others that you will encounter later. (However, note that the private modifier can only be applied to Nested Classes.)
    2. The class name, with the initial letter capitalized by convention.
    3. The name of the class's parent (superclass), if any, preceded by the keyword extends. A class can only extend (subclass) one parent.
    4. A comma-separated list of interfaces implemented by the class, if any, preceded by the keyword implements. A class can implement more than one interface.
    5. The class body, surrounded by braces, {}.

- Declaring Member Variables

-  kinds of variables:
   - Member variables in a class—these are called fields.
   - Variables in a method or block of code—these are called local variables.
   - Variables in method declarations—these are called parameters.
-  public modifier—the field is accessible from all classes.
-  private modifier—the field is accessible only within its own class.
-  the first letter of a class name should be capitalized, and
-  the first (or only) word in a method name should be a verb.

- method declaration:

```java
public double calculateAnswer(double wingSpan, int numberOfEngines,
                              double length, double grossTons) {
    //do the calculation here
}
```
- method declarations have six components, in order:

    1. Modifiers—such as public, private, and others you will learn about later.
    1. The return type—the data type of the value returned by the method, or void if the method does not return a value.
    1. The method name—the rules for field names apply to method names as well, but the convention is a little different.
    1. The parameter list in parenthesis—a comma-delimited list of input parameters, preceded by their data types, enclosed by parentheses, (). If there are no parameters, you must use empty parentheses.
    1. An exception list—to be discussed later.
    1. The method body, enclosed between braces—the method's code, including the declaration of local variables, goes here.

## [Binary, Decimal and Hexadecimal Numbers](https://www.mathsisfun.com/binary-decimal-hexadecimal.html)


### Decimals

- Every digit in a decimal number has a "position", and the decimal point helps us to know which position is which
   - ![Decimals](https://www.mathsisfun.com/numbers/images/decimal.svg)

### Bases

- there is 10 symbols:
   - 0, 1, 2, 3, 4, 5, 6, 7, 8 and 9
- In binary you count "0,1,..." but then you run out of symbols! So you add 1 on the left and then start again at 0: 10,11 ...
- general rule is Count up until just before the "Base Number", then start at 0 again, but first you add 1 to the number on your left.

### Binary Numbers

- Binary Numbers are just "Base 2" instead of "Base 10". So you start counting at 0, then 1, then you run out of digits

### Hexadecimal Numbers

- They look the same as the decimal numbers up to 9, but then there are the letters ("A',"B","C","D","E","F") in place of the decimal numbers 10 to 15.