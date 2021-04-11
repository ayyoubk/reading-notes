# Problem Domain, Objects, and the DOM

***Problem domain is a term referring to all information that defines the problem and constrains the solution (the constraints being part of the problem). It includes the goals that the problem owner wishes to achieve, the context within which the problem exists, and all rules that define essential functions or other aspects of any solution product. It represents the environment in which a solution will have to operate, as well as the problem itself.***


## JS Chapter 3: “Object Literals”

***Objects group together a set of variables and functions to create a model of a something you would recognize from the real world. In an object, variables and functions take on new names.***

*there are several ways to create objects, literal notation is the most  popular way.*

```
var hotel ={
    name: 'hotelName', 
    rooms: 40,
    booked: 25,
    checkRoom: function(){
        return this.room  - this booked;
    }
}
```

|Object  | Key | Value |
|--|--|--|
| hotel | name | 'name of hotel' |
| - | rooms | '40' |
| - | booked | '25' |

*You access the properties or methods of an object using dot notation.*

```
var hotelName = hotel.name;
var roomsfree = hotel.checkRoom();
```

*You can also access properties using square brackets.*

```
var hotelName = hotel['name'];
```



## JS Chapter 5: “Document Object Model”

 ***The Document Object Model (DOM) specifies how browsers should create a model of an HTML page and how JavaScript can access and update the contents of a web page while it is in the browser window.***

*As a browser loads a web page, it creates a model of that page. The model is called a **DOM tree**, and it is stored in the browsers' memory. It consists of four main types of nodes.*

 1. DOCUMENT NODE
 2. ELEMENT NODES
 3. ATTRIBUTE NODES
 4. TEXT NODES

***DOM queries** are the methods that find element in the DOM tree*

*Storing elements in variables = storing the location of the element within the DOM tree in a variable*

```
var itemOne = getElementById ('one');
```

*But to access the content of the element use the variable name `itemOne.textContent`*

*`getElementById()` and `querySelector()` can both search an entire document and return individual elements.(both use a similar syntax)*


