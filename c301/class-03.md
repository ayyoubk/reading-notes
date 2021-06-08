## Passing Functions as Props


### React Docs - lists and keys
1. What does.map() return? 
its always return new array of the same length as the original array that contain your return values.
2. If I want to loop through an array and display each value in JSX, how do I do that in React?
 "You can build collections of elements and include them in JSX using curly braces {}."
3.  Each list item needs a unique  ***key***. 
4. What is the purpose of a key?
 "Keys help React identify which items have changed, are added, or are removed. Keys should be given to the elements inside the array to give the elements a stable identity"




### spread operator
1. What is the spread operator?
 syntax used to add elements to arrays, merge arrays or objects, and propagate an array into function argument suses of an ellipsis of three dots.
 2.  List 4 things that the spread operator can do.

* The spread syntax “spreads” the array into separate arguments
* copy an array or combine arrays
* Using an array as arguments
* Adding to state in React

3. Give an example of using the spread operator to combine two arrays.

~~~
const myArray = [`🤪`,`🐻`,`🎌`]
const yourArray = [`🙂`,`🤗`,`🤩`]
const ourArray = [...myArray,...yourArray]
console.log(...ourArray) // 🤪 🐻 🎌 🙂 🤗 🤩
~~~

4. Give an example of using the spread operator to add a new item to an array.

~~~
const myArray = [`🤪`,`🐻`,`🎌`]
const ourArray = [...myArray,...`🤩`]
~~~

5. Give an example of using the spread operator to combine two objects into one.


~~~
const objectOne = {hello: "🤪"}
const objectTwo = {world: "🐻"}
const objectThree = {...objectOne, ...objectTwo, laugh: "😂"}
console.log(objectThree) // Object { hello: "🤪", world: "🐻", laugh: "😂" }
const objectFour = {...objectOne, ...objectTwo, laugh: () => {console.log("😂".repeat(5))}}
objectFour.laugh() // 😂😂😂😂😂
~~~

### How to Pass Functions Between Components

 1. what is the first step that the developer does to pass functions between components?
 - creat function calls increment to pass an obj In your own words.
 2.  what does the increment function do?
 - loop throu this.state.people to check the name if it s match the name that passed in will encreas the counter that inside the obj.
 3.  How can you pass a method from a parent component into a child component?
  - add this.props.increment`(this.props.name)`.
 4. How does the child component invoke a method that was passed to it from a parent component?
  - `super(props) add increment={this.increment}`