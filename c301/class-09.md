# FUNCTIONAL PROGRAMMING

## Functional Programming Concepts

1- ***What is functional programming?***

- *Functional programming is a programming paradigm — a style of building the structure and elements of computer programs — that treats computation as the evaluation of mathematical functions and avoids changing-state and mutable data*

2- ***What is a pure function and how do we know if something is a pure function?***

- *A pure function is a function which:*

1. Given the same input, will always return the same output.
2. Produces no side effects.

3- ***What are the benefits of a pure function?***

- *One of the major benefits of using pure functions is they are immediately testable. They will always produce the same result if you pass in the same arguments.*

4- ***What is immutability?***

- *Immutable data cannot change its structure or the data in it. It's setting a value on a variable that cannot change, making that value a fact, or sort of like a source of truth — the same way a princess kisses a frog hoping it will turn into a handsome prince.*

5- ***What is Referential transparency?***

- *In functional programming, referential transparency is generally defined as the fact that an expression, in a program, may be replaced by its value (or anything having the same value) without changing the result of the program.*


## Modules and require()

1- ***What is a module?***

- *Module in Node. js is a simple or complex functionality organized in single or multiple JavaScript files which can be reused throughout the Node. js application. Each module in Node. js has its own context, so it cannot interfere with other modules or pollute global scope.*

2- ***What does the word ‘require’ do?***

- *It resolves libraries and modules in the Node search path.*

3- ***How do we bring another module into the file the we are working in?***

- *We use `reqiure()` to import that module.*

4- ***What do we have to do to make a module available?***

- *Use module.export inside the module itself*

### References:

- [Concepts of Functional Programming in Javascript](https://medium.com/the-renaissance-developer/concepts-of-functional-programming-in-javascript-6bc84220d2aa)

- [Node JS Tutorial for Beginners #6 - Modules and require()](https://www.youtube.com/watch?v=xHLd36QoS4k)

