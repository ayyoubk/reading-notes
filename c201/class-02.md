# Basics of HTML, CSS & JS

## Chapter 2: “Text”

**Headings** 
```
<h1>,<h2>,<h3>,<h4>,<h5>,<h6>
```
*Browsers display the contents of headings at different sizes. The contents of an `<h1>` element is the largest, and the contents of an `<h6>` element is the smallest.*

**Paragraphs** `<p>`
*To create a paragraph, surround the words that make up the paragraph with an opening `<p>` tag and closing `</p>` tag.*

**Bold & Italic**

*By enclosing words in the tags `<b>` and `</b>` we can make characters appear bold.*

*By enclosing words in the tags `<i>` and `</i>` we can make characters appear italic.*

**Superscript & Subscript**

*The `<sup>` element is used to contain characters that should be superscript such as the suffixes of dates or mathematical concepts like raising a number to a power such as $n^2$ .*

*The `<sub>` element is used to contain characters that should be subscript. It is commonly used with foot notes or chemical formulas such as H<sub>2</sub>O.*

**Line Breaks & Horizontal Rules**

*if you wanted to add a line break inside the middle of a paragraph you can use the line break tag `<br />` .*

*To create a break between themes you can add a horizontal rule between sections using the `<hr />` tag.*

**Semantic Markup**

*There are some text elements that are not intended to affect the structure of your web pages, but they do add extra information to the pages*

**Strong & Emphasis**

*The use of the `<strong>` element indicates that its content has strong importance. For example, the words contained in this element might be said with strong emphasis.*
*By default, browsers will show the contents of a `<strong>` element in bold.*

*The `<em>` element indicates emphasis that subtly changes the meaning of a sentence. By default browsers will show the contents of an `<em>` element in italic.*

**Quotations**

*The `<blockquote>` element is used for longer quotes that take up an entire paragraph. Note how the `<p>` element is still used inside the `<blockquote>` element.*

*The `<q>` element is used for shorter quotes that sit within a paragraph. Browsers are supposed to put quotes around the `<q>` element, however Internet Explorer does not — therefore many people avoid using the `<q>` element.*

## Chapter 10: Ch.10 “Introducing CSS”

*CSS works by associating rules with HTML elements. These rules govern how the content of specified elements should be displayed. A CSS rule contains two parts: a selector and a declaration.*

```
p {
font-family: Arial;}
```

*CSS declarations sit inside curly brackets and each is made up of two parts: a property and a value, separated by a colon. You can specify several properties in one declaration, each separated by a semi-colon.*

*The `<link>` element can be used in an HTML document to tell the browser where to find the CSS file used to style the page. It is an empty element, and it lives inside the <head> element. It should use three attributes:*

- ***href** This specifies the path to the CSS file (which is often placed in a folder called css or styles).*
- ***type** This attribute specifies the type of document being linked to. The value should be text/css.*
- ***rel** This specifies the relationship between the HTML page and the file it is linked to. The value should be stylesheet when linking to a CSS file.*
 
