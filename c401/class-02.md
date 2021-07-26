# Read: 02 - Arrays, Loops, Imports

## [Java Imports](https://perso.ensta-paris.fr/~diam/java/online/notes-java/language/10basics/import.html)

1. Java classes can be grouped together in packages
1. Package = directory (A package name is the same as the directory (folder) name which contains the .java files)
1. The first statement must be the package declaration.
1. After importing a package you can specify classes from that package
   1.For small programs it's common to omit the package declaration ,in which case Java creates what it calls a default package although it is not recommended to use it.
1. Package declaration syntax :

   - Package statment (optional). ex : `package illustration;`
   - Imports (optional). ex: `import java.awt.*;`
   - Class or interface definitions.
     ex:

   ```
   public class Drawing {
     . . .
   }
   ```

1. The wildcard character (\*) is used to specify that all classes with that package are available to your program.
1. Common imports:

   - import java.awt.\*; Common GUI elements.
   - import java.awt.event.\*; The most common GUI event listeners.
   - import javax.swing.\*; More common GUI elements. Note "javax".
   - import java.util.\*; Data structures (Collections), time, Scanner, etc classes.
   - import java.io.\*; Input-output classes.
   - import java.text.\*; Some formatting classes.
   - import java.util.regex.\*; Regular expression classes.

1. importing all classes in a package doesn't make my object file (.class or .jar) larger.
1. The wildcard "\*" only makes the classes in this package visible.
1. All classes in the java.lang package are visible without an import. ex :String, System ...
1. Static imports in Java 5 leads to name pollution and confusion about which class constants come from.

## [Different types of loops in Java](https://www.baeldung.com/java-loops)

**_In programming languages, looping is a feature which facilitates the execution of a set of instructions until the controlling Boolean-expression evaluates to false._**

Here are the types of loops that we can find in Java:

- Simple for loop : allows us to repeat certain operations by incrementing and evaluating a loop counter.
- Enhanced for-each loop
- While loop : it repeats a statement or a block of statements while its controlling Boolean-expression is true.
- Do-While loop :works just like the while loop except for the fact that the first condition evaluation happens after the first iteration of the loop.
