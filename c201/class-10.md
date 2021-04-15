# Debugging

## JavaScript book, Ch. 10, “Error Handling & Debugging”

***JavaScript interpreter processes one line of code at a time.***

***The Stack** is the process that happened when any statement needs data from another function so the new process stacks over the previous statement.*

*Each time a script enters a new execution context, there are two phases of activity:*

1. *Prepare*
    - The new scope is created
    - Variables, functions, and arguments are created
    - The value of the this keyword is determined

2. *Execute*
    - Now it can assign values to variables
    - Reference functions and run their code
    - Execute statements

> Debugging is about deduction: eliminating potential causes of an error.

***The JavaScript console will tell you when there is a problem with a script, where to look for the problem, and what kind of issue it seems to be.The JavaScript console is just one of severa l developer tools that are found in all modern browsers.***

***The `console.log()` method can write several values to the console at the same t ime, each separated by a comma***

- `conso1e.info()` can be used for general information
- `console.warn()` can be used for warnings
- `console.error()` can be used to hold errors

*If you want to write a set of related data to the console, you can use the `console.group()` method to group the messages together. to indicate the end of the group the `console.groupEnd ()`*

*the `console.table()` method lets you output a table showing:*
- objects
- arrays that contain other objects or arrays

