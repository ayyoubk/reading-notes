# HTML Lists, Control Flow with JS, and the CSS Box Model

## Chapter 3: “Lists”

***HTML provides three different types:***

- *Ordered lists*
- *Unordered lists*
- *Definition lists*

*The ordered list is created with the `<ol>` element, Each item in the list is placed between an opening `<li>` tag and a closing `</li>` tag.*

*The unordered list is created with the `<ul>` element. Each item in the list is placed between an opening `<li>` tag and a closing `</li>` tag.*

*The definition list is created with the `<dl>` element and usually consists of a series of terms and their definitions.Inside the `<dl>` element you will usually see pairs of `<dt>` (the definition term) and `<dd>` (contain the definition) elements.*

***Note: Lists can be nested inside one another.***

## Chapter 13: “Boxes”

***CSS treats each HTML element as if it lives in its own box.***

*To set your own dimensions for a box you can use the **height** and **width** properties.*

*The **min-width** property specifies the smallest size a box can be displayed at when the browser window is narrow, and the **max-width** property indicates the maximum width a box can stretch to when the browser window is wide.*

```
min-width, max-width, min-height, max-height
```

*The **overflow** property tells the browser what to do if the content contained within a box is larger than the box itself. It can have one of two values:*

- *`hidden` This property simply hides any extra content that does not fit in the box.*
- *`scroll` This property adds a scrollbar to the box so that users can scroll to see the missing content.*

**Every box has three available properties that can be adjusted to control its appearance:**

- *Padding*
- *Border*
- *Margin*

*We can used it with width and control all dimensions around any box.*

**The display property can take many value like:**
- *`inline` This causes a block-level element to act like an inline element.*
- *`block` This causes an inline element to act like a block-level element.*
- *`inline-block` This causes a block-level element to flow like an inline element, while retaining other features of a block-level element.*
- *`none` This hides an element from the page.(the content of the box can be seen if used the view source option*


## (JS book) 

***JavaScript arrays (special variables) are used to store multiple values in a single variable.***
```
var cars = ["Saab", "Volvo", "BMW"];
// Update the third item in the array
colors[2] = 'Audi' ;
```

***The JavaScript Switch Statement : Use the switch statement to select one of many code blocks to be executed.***

```
switch(expression) {
  case x:
    // code block
    break;
  case y:
    // code block
    break;
  default:
    // code block
}
```

***This is how it works:***

- *The switch expression is evaluated once.*
- *The value of the expression is compared with the values of each case.*
- *If there is a match, the associated block of code is executed.*
- *If there is no match, the default code block is executed.*


*JavaScript can convert data types behind the scenes to complete an operation. This is known as **type coercion**.*

| DATA TYPE | PURPOSE |
|--|--|
| string | Text |
| Number| Number |
| Boolean| true or false|
| null | Empty value|
| undefined| Variable has been declared but not yet assigned a value|

