# Read: 11 - Spring

## [Spring App Basics](https://spring.io/guides/gs/serving-web-content/)

- This guide walks you through the process of creating a “Hello, World” web site with Spring.
- build an application that has a static home page and that will also accept HTTP GET requests
- It will respond with a web page that displays HTML. The body of the HTML will contain a greeting: “Hello, World!”
- Starting with Spring Initializr
    - If you use Gradle, visit the Spring Initializr to generate a new project with the required dependencies (Spring Web, Thymeleaf, and Spring Boot DevTools).
- Spring Boot Devtools is handy module to speed up this refresh cycle
    - Enables hot swapping.
    - Switches template engines to disable caching.
    - Enables LiveReload to automatically refresh the browser.
    - Other reasonable defaults based on development instead of production.

- HTTP requests are handled by a **controller**, to identify the controller use the `@Controller `annotation.
- The `@GetMapping` annotation ensures that HTTP GET requests to the route (for example `/greeting`) are mapped to the `greeting()` method.

- `@RequestParam` binds the value of the query string parameter, this parameter can be `required` or not and it take `defaultValue` in case params is absent.

- To test the Application just visit your local host where you should see “Hello, World!”


## [Spring MVC and Thymeleaf](https://www.thymeleaf.org/doc/articles/springmvcaccessdata.html)

***A Spring MVC is a Java framework which is used to build web applications***

- `@Controller` classes are responsible for preparing a model map with data and selecting a view to be rendered

- Adding Model attributes can be done in several ways :
    - Add attribute to Model via its `addAttribute` method

      ```java
      @RequestMapping(value = "message", method = RequestMethod.GET)
            public String messages(Model model) {
                  model.addAttribute("messages", messageRepository.findAll());
                  return "message/list";
            }
      ```

    - By returning `ModelAndView` with model attributes included

      ```java
         @RequestMapping(value = "message", method = RequestMethod.GET)
            public ModelAndView messages() {
                  ModelAndView mav = new ModelAndView("message/list");
                  mav.addObject("messages", messageRepository.findAll());
                  return mav;
            }
      ```

    - Expose common attributes via methods annotated with `@ModelAttribute`

      ```java
         @ModelAttribute("messages")
            public List<Message> messages() {
                  return messageRepository.findAll();
            }
      ```

- All these attributes can be accessed by thymeleaf templates .

- Model attributes can be accessed from thymeleaf by the following syntax ${attribute name} .

- You can access request parameters easily from thyme leaf using param prefix .

- When multivalued param is passed will return a serialized array until the unless condition .

- #request is also a good approach to access request parameters .

- Adding HTTPSession object to the parameters of the request method will make it accesible from thymeleaf using the session prefix .

- Servile contexts are shared between requests and sessions and can be accessed using #servletContext prefix .

- Accessing Spring beans can be easily done using `@beanname` syntax .
