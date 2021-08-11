# Read: 13 - Related Resources and Integration Testing

## [Related data in Spring](https://www.baeldung.com/spring-data-rest-relationships)

- One-to-One Relationship
   - Two entity classes can have a one to one relationship using the `@OneToOne` annotation, and the association will be owned by the first entity class by the end of the association.
  - `@RestResource` annotation is optional and can be used to customize the endpoint.
   - Make sure to have different names for each association resource.
   - To expose these entities as resources, create two repository interfaces for each of them, by extending the CrudRepository interface.
   - To create the resources add an instance, and have the API return the JSON object. Next send a GET request to the endpoint, which will return an empty object. Create the association using the HTTP method PUT and a body containing the URI of the resource to bind to the association. If you need to remove an association, we can call the endpoint with DELETE method.
- One-to-Many Relationship
   - One-to-many relationship - defined using the `@OneToMany` and `@ManyToOne` annotations and can have the optional `@RestResourc`e annotation to customize the association resource
   - example: there are many books in the library
- Many-to-Many Relationship
   - Many-to-many relationship - defined using `@ManyToMany` annotation, to which we can add `@RestResource`.
   - example there are many authors for many books

- Testing the Endpoints With TestRestTemplate
   - Create a test class that injects a TestRestTemplate instance and defines the constants we will use.
   - Testing the One-to-One Relationship - create a `@Test` method that saves objects by making POST requests to the collection resources. Then save the relationship with a PUT request to the association resource and verifies that it has been established with a GET request to the same resource.
   - Testing the One-to-Many Relationship - create a `@Test` method that saves a instance and two other instances, send a PUT request to each object's association resource, and verify that the relationship has been saved.
   - Testing the Many-to-Many Relationship - create a test method that saves one record and two other records. Then it sends a PUT request to the association resource with the two URIs and verifies that the relationship has been established.

## [Spring Integration Testing](https://www.baeldung.com/integration-testing-in-spring)

- Several dependencies are required for running the integration tests :
   - Spring Test.
   - Junit Jupiter.

- Enable Spring in Tests with JUnit 5
   - We can enable this extension by adding the @ExtendWith annotation to our test classes and specifying the extension class to load. To run the Spring test, we use SpringExtension.class.
   - We also need the @ContextConfiguration annotation to load the context configuration and bootstrap the context that our test will use.
   - Finally, we also annotate the test with @WebAppConfiguration, which will load the web application context.
- WebApplicationContext provides a web application configuration. It loads all the application beans and controllers into the context. We use the Web application context annotation to wire the object of it which will add all the beans, controllers and classes.
- MockMvc provides support for Spring MVC testing. It encapsulates all web application beans and makes them available for testing.
- To Verify testing configuration we should verify that :

   - Check if web application context is loaded.
   - Check the right servlet context is instance of the web application context.

- Verify View Name

   - `perform()` method will call a GET request method, which returns the ResultActions. Using this result, we can have assertion expectations about the response, like its content, HTTP status, or header
   - `andDo(print())` will print the request and response. This is helpful to get a detailed view in case of an error
   - `andExpect()` will expect the provided argument. In our case, we're expecting “index” to be returned via `MockMvcResultMatchers.view()`
- Verify Response Body

   - `andExpect(MockMvcResultMatchers.status().isOk())` will verify that response HTTP status is Ok (200).
   - an`dExpect(MockMvcResultMatchers.jsonPath(“$.message”).value(“Hello World!!!”))` will verify that response content matches with the argument “Hello World!!!“.
   - `andReturn()` will return the MvcResult object, which is used when we have to verify something that isn't directly achievable by the library. In this case, we've added `assertEquals` to match the content type of the response that is extracted from the MvcResult object
- Send GET Request With Path Variable

   - `MockMvcRequestBuilders.get(“/greetWithPathVariable/{name}”, “John”)` will send a request as “/greetWithPathVariable/John“.
- Send GET Request With Query Parameters

   - `param(“name”, “John Doe”)` will append the query parameter in the GET request. This is similar to “/greetWithQueryVariable?name=John%20Doe“.
- Send POST Request

   - `MockMvcRequestBuilders.post(“/greetWithPost”)` will send the POST request. We can set path variables and query parameters in a similar way as before, whereas form data can be set only via the param() method, similar to query parameters
   - 