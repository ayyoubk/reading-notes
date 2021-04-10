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

 You can also access properties using square brackets.

 `var hotelName = hotel['name'];`


 ## JS Chapter 5: “Document Object Model”

 ***The Document Object Model (DOM) specifies how browsers should create a model of an HTML page and how JavaScript can access and update the contents of a web page while it is in the browser window.***




