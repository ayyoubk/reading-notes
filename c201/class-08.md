# CSS Layout 

## Ch. 15

***We use Layout to:***

- *Controlling the position of elements*
- *Creating site layouts*
- *Designing for different sized screens*

***CSS treats each HTML element as if it is in its own box. This box will either be a block-level box or an inline box.***

*Block-level elements start on a new line Examples include: `<h1> <p> <ul> <li>`*

*Inline elements flow in between surrounding text Examples include:`<img> <b> <i>`*

*containing or parent element is the outer box that contain one or more block-level inside it.*

***positioning schemes** that allow you to control the layout of a page: normal flow, relative positioning, and absolute positioning by using the position property in CSS*

- *Normal flow this is the default behavior for block-level element that appears on a new line*
- *Relative Positioning This moves an element from the position it would be in normal flow, shifting it to the top, right, bottom, or left of where it would have been placed (without affect the position of surrounding elements)*
- *Absolute positioning This positions the element in relation to its containing element. Absolutely positioned elements move as users scroll up and down the page*
- *Fixed Positioning This is a form of absolute positioning that positions the element in relation to the browser window (do not move when the user scrolls up or down the page)*
- *Floating Elements Floating an element allows you to take that element out of normal flow and position it to the far left or right of a containing box.*

*If boxes overlap use the `z-index` property allows you to control which box appears on top.*

*The `float` property allows you to take an element in normal flow and place it as far to the left or right of the containing element as possible.*

*The clear property allows you to say that no element (within the same containing element) should touch the left or righthand sides of a box. It can take the following values: (left , ight, both, none)*

***Screen Sizes different visitors to your site will have different sized screens that show different amounts of information.***

*Designers keep pages within 960-1000 pixels wide, and indicate what the site is about within the top 600 pixels (to demonstrate its relevance without scrolling).*