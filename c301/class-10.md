# In memory storage

## Understanding the JavaScript Call Stack

***1- What is a ‘call’?***

- *A call stack is a mechanism for an interpreter (like the JavaScript interpreter in a web browser) to keep track of its place in a script that calls multiple functions — what function is currently being run and what functions are called from within that function.*

2- ***How many ‘calls’ can happen at once?***

- *On at a time*

3- ***What does LIFO mean?***

- *It stands for Last In First Out and it means the last function enters the stack will execute first*

4- ***Draw an example of a call stack and the functions that would need to be invoked to generate that call stack.***

![callstack](https://vaibhavguptame.files.wordpress.com/2018/01/callstack.gif?w=349)

5- ***What causes a Stack Overflow?***

- *A stack overflow occurs when there is a recursive function (a function that calls itself) without an exit point. The browser (hosting environment) has a maximum stack call that it can accomodate before throwing a stack error. ... The callMyself() will run until the browser throws a “Maximum call size exceeded”.*

## JavaScript error messages

1- ***What is a ‘refrence error’?***

- This is as simple as when you try to use a variable that is not yet declared you get this type os errors

2- ***What is a ‘syntax error’?***

- The SyntaxError object represents an error when trying to interpret syntactically invalid code. It is thrown when the JavaScript engine encounters tokens or token order that does not conform to the syntax of the language when parsing code.

3- ***What is a ‘range error’?***

- It means that somewhere in your code, you are calling a function which in turn calls another function and so forth, until you hit the call stack limit. This is almost always because of a recursive function with a base case that isn't being met.

4- ***What is a ‘tyep error’?***

- The TypeError object represents an error when an operation could not be performed, typically (but not exclusively) when a value is not of the expected type. A TypeError may be thrown when: an operand or argument passed to a function is incompatible with the type expected by that operator or function.

5- ***What is a breakpoint?***

- At each breakpoint, JavaScript will stop executing, and let you examine JavaScript values. After examining values, you can resume the execution of code (typically with a play button).

6- ***What does the word ‘debugger’ do in your code?***

-The debugger statement stops the execution of JavaScript, and calls (if available) the debugging function. Using the debugger statement has the same function as setting a breakpoint in the code. Normally, you activate debugging in your browser with the F12 key, and select "Console" in the debugger menu.
