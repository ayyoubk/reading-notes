# Read: 12 - Spring RESTful Routing & Static Files

## [Baeldung: Spring Request Mapping](https://www.baeldung.com/spring-requestmapping)

***`@RequestMapping` this annotation is used to map web requests to Spring Controller methods***

- `@RequestMapping` — by Path :

```java
@RequestMapping(value = "/ex/foos", method = RequestMethod.GET)
@ResponseBody
public String getFoosBySimplePath() {
    return "Get some Foos";
}
```

- `@RequestMapping` With the headers Attribute:


```java
@RequestMapping(value = "/ex/foos", headers = "key=val", method = GET) // or multi headers headers = { "key1=val1", "key2=val2" }
@ResponseBody
public String getFoosWithHeader() {
    return "Get some Foos with Header";
}
```

- RequestMapping With Path Variables

   - Single `@PathVariable`

      ```java
      @RequestMapping(value = "/ex/foos/{id}", method = GET)
      @ResponseBody
      public String getFoosBySimplePathWithPathVariable(
      @PathVariable("id") long id) {
      return "Get a specific Foo with id=" + id;
      }
      ```

   - Multiple `@PathVariable`

      ```java
      @RequestMapping(value = "/ex/foos/{fooid}/bar/{barid}", method = GET)
      @ResponseBody
      public String getFoosBySimplePathWithPathVariables
      (@PathVariable long fooid, @PathVariable long barid) {
         return "Get a specific Bar with id=" + barid + 
            " from a Foo with id=" + fooid;
      }
      ```

   - `@PathVariable` With Regex

      For example, we will restrict the mapping to only accept numerical values for the id:

      ```java
      @RequestMapping(value = "/ex/bars/{numericId:[\\d]+}", method = GET)
      @ResponseBody
      public String getBarsBySimplePathWithPathVariable(
      @PathVariable long numericId) {
      return "Get a specific Bar with id=" + numericId;
      }
      ```

- RequestMapping With Request Parameters

  - `@RequestMapping` allows easy mapping of URL parameters with the `@RequestParam` annotation.

      ```java
      // http://localhost:8080/spring-rest/ex/bars?id=100
      @RequestMapping(value = "/ex/bars", method = GET)
      @ResponseBody
      public String getBarBySimplePathWithRequestParam(
      @RequestParam("id") long id) {
         return "Get a specific Bar with id=" + id;
      }
      ```
      - or
      ```java
      @RequestMapping(value = "/ex/bars", params = "id", method = GET)
      @ResponseBody
      public String getBarBySimplePathWithExplicitRequestParam(
      @RequestParam("id") long id) {
         return "Get a specific Bar with id=" + id;
      }
      ```

- RequestMapping Corner Cases

   - `@RequestMapping` — Multiple Paths Mapped to the Same Controller Method

      ```java
      @RequestMapping(
      value = { "/ex/advanced/bars", "/ex/advanced/foos" }, 
      method = GET)
      @ResponseBody
      public String getFoosOrBarsByPath() {
         return "Advanced - Get some Foos or Bars";
      }
      ```

   - `@RequestMapping` — Multiple HTTP Request Methods to the Same Controller Method

      ```java
      @RequestMapping(
      value = "/ex/foos/multiple", 
      method = { RequestMethod.PUT, RequestMethod.POST }
      )
      @ResponseBody
      public String putAndPostFoos() {
         return "Advanced - PUT and POST within single method";
      }
      ```

- New Request Mapping Shortcuts: 
  - `@GetMapping`
  - `@PostMapping`
  - `@PutMapping`
  - `@DeleteMapping`
  - `@PatchMapping`

## [Spring guide: Accessing Data with JPA](https://spring.io/guides/gs/accessing-data-jpa/)

***Spring Data JPA, part of the larger Spring Data family***

- Start with Spring Initializr, and once that is set up define a simple entity.
- Starts by defining a class with it's members and constructor including getters and setters if wanted .
- Then You have to annotate the class with @Entity annotation .
- After that start by adding an id as a data member annotated with @Id and @GeneratedValue with (strategy = GenerationType.Auto) This means that the id value will be generated automatically .
- In entity the default constructor must be declared .
- The arg-Constructor is used to create objects and save in the database 

- Create Simple Queries
  - In order to make queries and operation to the entity we should make a new repository interface .
  - That interface should extend JpaRepository to take all the operations on the database from Jpa .
  - In that interface you are allowed to define methods by adding their signature to the interface .
  - You can add data to the database by making an object of the entity class .
  - Then use the save method to save the object in the database .

- Then create simple queries. Spring Data JPA focuses on using JPA to store data in a relational database, and one of its abilities is to create repository implementations automatically.
- Next, Spring Initializer creates a simple class for the application.
- Build an executable JAR that contains all the necessary dependencies, classes, and resources and run that. Building an executable jar makes it easy to ship, version, and deploy the service as an application throughout the development lifecycle, across different environments, and so forth.

## [Baeldung: Comparing repositories](https://www.baeldung.com/spring-data-repositories)

***Every repository in Spring Data extends the generic Repository interface, but beyond that, they do each have different functionality***

- Spring Data Repositories
    - CrudRepository - provides CRUD functions
    - PagingAndSortingRepository - provides methods to do pagination and sort records
    - JpaRepository - provides JPA related methods such as flushing the persistence context and delete records in a batch, and contains the full API of CrudRepository and PagingAndSortingRepository due to their inheritance relationship
- CrudRepository - the typical CRUD functionality:
    - save(…) – save an Iterable of entities. Here, we can pass multiple objects to save them in a batch
    - findOne(…) – get a single entity based on passed primary key value
    - findAll() – get an Iterable of all available entities in database
    - count() – return the count of total entities in a table
    - delete(…) – delete an entity based on the passed object
    - exists(…) – verify if an entity exists based on the passed primary key value
- PagingAndSortingRepository - extends CrudRepository, provides a method, and you cancreate an object with certain properties.
- JpaRepository methods:
    - indAll() – get a List of all available entities in database
    - findAll(…) – get a List of all available entities and sort them using the provided condition
    - save(…) – save an Iterable of entities. Here, we can pass multiple objects to save them in a batch
    - flush() – flush all pending task to the database
    - saveAndFlush(…) – save the entity and flush changes immediately
    - deleteInBatch(…) – delete an Iterable of entities
- Downsides of Spring Data Repositories
    - We couple our code to the library and to its specific abstractions, but we do have to be careful not to expose these internal implementation details.
    - By extending a repository we expose a complete set of persistence method at once,but we might run into situations where we'd like to gain more fine-grained control over the methods exposed.
