# React and Forms

**What is a "Controlled Component"?**

An input form element whose value is controlled by React in this way is called a “controlled component”.In HTML, form elements such as `<input>`, `<textarea>`, and `<select>` typically maintain their own state and update it based on user input. In React, mutable state is typically kept in the state property of components, and only updated with setState().

**forms:**

* The `<FormControl>` component renders a form control with Bootstrap styling

* The `<FormControl>` component directly renders the `<input>` or other specified component.
* If your application contains a large number of form groups, we recommend building a higher-level component encapsulating a complete field group that renders the label, the control, and any other necessary components.
* Provide valuable, actionable feedback to your users with form validation feedback.

**Should we wait to store the users responses from the form into state when they submit the form OR should we update the state with their responses as soon as they enter them? Why.**

no Specifying the value prop on a controlled component prevents the user from changing the input unless you desire so. If you’ve specified a value but the input is still editable, you may have accidentally set value to undefined or null.

**How do we target what the user is entering if we have an event handler on an input field?**
 `handleChange(event) { this.setState({value: event.target.value}); }` 

**Why would we use a ternary operator?**

beacuse it's shortened way of writing an if-else statement, by writing one line of code with three arguments, the condition, the result upon the true comparison, and the result upon the false comparison.

Rewrite the following statement using a ternary statement:

~~~
if(x===y){
console.log(true);
} else {
console.log(false);
}
~~~
The answer:
~~~
let answer= ((x===y)? 'true': 'false');
~~~