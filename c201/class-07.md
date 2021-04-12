# HTML Tables; JS Constructor Functions

## HTML Chapter 6: “Tables”

***The `<table>` element is used to create a table. The contents of the table are written out row by row.***

***`<tr>` to indicate the start of each row***

***Each cell of a table is represented using a `<td>` element.***

***The `<th>` element is used just like the `<td>` element but its purpose is to represent the heading for either a column or a row.***

***colspan="value"** attribute with value work like merge cell horizontally*

***rowspan="value"** attribute with value work like merge cell vertically*

***For long tables you can split the table into a `<thead>`, `<tbody>`, and `<tfoot>`.***


## JS Chapter 3: “Functions, Methods, and Objects” 

```
var hotel = new Object();
```

***the `new` keyword with Object constructor create new blank object, after this we can add properties and methods to it by dot notation***

```
hotel.rooms = 40;
hotal.check = function() {
    // block of code ;
}
```

***to delete property use `delete` keyword befor `hotel.rooms`***

***If you want several objects to represent similar things, First, create the template with the object's properties and methods.***


```
function Hotel (name, rooms, booked) {
    this.name = name;
    this.rooms = rooms;
    this.booked = booked;
    this.checkAvailability = function() {
        return this.rooms - this . booked;
    };
}
```
***then you can create the same object as you want***

```
var parkHotel = new Hotel('Park',40,25)
// and
var greenHotel = new Hotel('Green',20,7)
``
