# Read: 01 - Java Basics

## [Java Basics](https://docs.oracle.com/javase/tutorial/java/nutsandbolts/index.html)

### Bundling code into individual software objects provides a number of benefits, including

- Modularity: The source code for an object can be written and maintained independently of the source code for other objects. Once created, an object can be easily passed around inside the system.
- Information-hiding: By interacting only with an object's methods, the details of its internal implementation remain hidden from the outside world.
- Code re-use: If an object already exists (perhaps written by another software developer), you can use that object in your program. This allows specialists to implement/test/debug complex, task-specific objects, which you can then trust to run in your own code.
- Pluggability and debugging ease: If a particular object turns out to be problematic, you can simply remove it from your application and plug in a different object as its replacement. This is analogous to fixing mechanical problems in the real world. If a bolt breaks, you replace it, not the entire machine.

### Language Basics

1. Variables
   - Instance Variables (Non-Static Fields): their values are unique to each instance of a class
   - Class Variables (Static Fields): their values will never change.
   - Local Variables
   - Parameters
   - Variable names are case-sensitive
   - begin your variable names with a letter
   - dollar sign character, by convention, is never used
   - use full words instead of cryptic abbreviations
   - If it consists of more than one word, capitalize the first letter of each subsequent word
   - If your variable stores a constant value capitalize every letter and separating subsequent words with the underscore character
1. Operators
   - postfix expr++ expr--
   - unary ++expr --expr +expr -expr ~ !
   - multiplicative \* / %
   - additive + -
   - shift << >> >>>
   - relational < > <= >= instanceof
   - equality == !=
   - bitwise AND &
   - bitwise exclusive OR ^
   - bitwise inclusive OR |
   - logical AND &&
   - logical OR ||
   - ternary ? :
   - assignment = += -= \*= /= %= &= ^= |= <<= >>= >>>=
1. Expressions, Statements, and Blocks
   - An expression is a construct made up of variables, operators, and method invocations
   - Statements are roughly equivalent to sentences in natural languages. A statement forms a complete unit of execution
     - expression statements
     - declaration statements
     - control flow statements
   - A block is a group of zero or more statements between balanced braces and can be used anywhere a single statement is allowed.
1. Control Flow Statements
   - Control flow statements, break up the flow of execution by employing decision making, looping, and branching, enabling your program to conditionally execute particular blocks of code.

## [Reddit thread on compiling](https://www.reddit.com/r/explainlikeimfive/comments/233dq5/eli5_what_does_it_mean_to_compile_code/)

1. the compiler (usually another program) takes the program the human wrote, and converts it into the program the computer can understand (i.e. converts from Java to machine language). Or compile means to make the code executable.

## [Reading Java Documentation](https://www.dummies.com/programming/java/making-sense-of-javas-api-documentation/)

1. Searching for a term : You can find things in the API documentation in a number of different ways. Each way is convenient in one situation or another.

- [Using the index for search](https://docs.oracle.com/javase/8/docs/api/)
- [Or Using the list of classes for search](https://docs.oracle.com/javase/8/docs/api/)
