# Read: Class 03 Maps, primitives, File I/O

## [Primitives vs. Objects](https://www.baeldung.com/java-primitives-vs-objects)

***Java has a two-fold type system consisting of primitives such as int, boolean and reference types such as Integer, Boolean. Every primitive type corresponds to a reference type.***

```java
Integer j = 1;          // autoboxing
int i = new Integer(1); // unboxing
```

- wrapper classes are immutable (so that their state can't change once the object is constructed) and are final (so that we can't inherit from them).
- autoboxing: converting a primitive type to a reference.
- unboxing: converting a reference type to a primitive.

- Single Item Memory Footprint:
   - primitive types:
     - boolean – 1 bit
     - byte – 8 bits
     - short, char – 16 bits
     - int, float – 32 bits
     - long, double – 64 bits
   - reference types:
     - Boolean – 128 bits
     - Byte – 128 bits
     - Short, Character – 128 bits
     - Integer, Float – 128 bits
     - Long, Double – 192 bits

- The reference types are objects, they live on the heap and are relatively slow to access.
- primitive type live in the stack and hence are accessed fast.
- plot for arrays with the various number of elements for every type:

    ![Memory Footprint for Arrays](https://www.baeldung.com/wp-content/uploads/2018/08/plot-memory-bits.gif)

- arrays of the primitive types long and double consume more memory than their wrapper classes Long and Double
- single-element arrays of primitive types are almost always more expensive (except for long and double) than the corresponding reference type.
- For the wrapper classes, the default value is null.
- the reference types might acquire a value (null) that in some sense doesn't belong to their domains which may cause errors if they didn't get uninitialized.
- Java language specification doesn't allow usage of primitive types in the parametrized types (generics), in the Java collections or the Reflection API.

## [Exceptions in Java](https://docs.oracle.com/javase/tutorial/essential/exceptions/index.html)

### What Is an Exception?

- An exception is an event, which occurs during the execution of a program, that disrupts the normal flow of the program's instructions.
- The object that called an exception object, contains information about the error, including its type and the state of the program when the error occurred. Creating an exception object and handing it to the runtime system is called throwing an exception.
- call stack: the ordered list of methods that had been called to get to the method where the error occurred.
   - ![call stack](https://docs.oracle.com/javase/tutorial/figures/essential/exceptions-callstack.gif)
- exception handler: a block of code that can handle the exception
- when the runtime system exhaustively searches all the methods on the call stack without finding an appropriate exception handler it terminates the program
   - ![terminates](https://docs.oracle.com/javase/tutorial/figures/essential/exceptions-errorOccurs.gif)

### The Catch or Specify Requirement

- a code that might throw certain exceptions must be enclosed by either of the following:
   - A try statement that catches the exception.
   - A method that specifies that it can throw the exception. The method must provide a throws clause that lists the exception,
- Not all exceptions are subject to the Catch or Specify Requirement.
- The Three Kinds of Exceptions
   - checked exception: a well-written application should anticipate and recover from, All exceptions are checked exceptions, except for those indicated by `Error`, `RuntimeException`, and their subclasses
   - error: exceptional conditions that are external to the application, and that the application usually cannot anticipate or recover from
   - runtime exception: exceptional conditions that are internal to the application, and that the application usually cannot anticipate or recover from, indicate programming bugs, such as logic errors or improper use of an API.
- Errors and runtime exceptions are collectively known as unchecked exceptions.

### Catching and Handling Exceptions

- FileWriter constructor: If the file cannot be opened, the constructor throws an IOException.
- ArrayList class's get method, which throws an IndexOutOfBoundsException if the value of its argument is too small (less than 0) or too large (more than the number of elements currently contained by the ArrayList).
- the compiler prints an error message about the exception thrown by the FileWriter constructor. However, it does not display an error message about the exception thrown by get the reason is:
   - IOException, is a checked exception.
   - IndexOutOfBoundsException, is an unchecked exception.

## [Using Scanner to read in a file in Java](https://docs.oracle.com/javase/tutorial/essential/io/scanning.html)

- Objects of type Scanner are useful for breaking down formatted input into tokens and translating individual tokens according to their data type.
- By default, a scanner uses white space to separate tokens.
- White space characters include blanks, tabs, and line terminators
- Scanner's close is a method that invokes when it is done with the scanner object
- To use a different token separator, invoke `useDelimiter()`
