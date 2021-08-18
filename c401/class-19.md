# Read: 19 - Spring and Sockets

## [Using WebSocket to build an interactive web application](https://spring.io/guides/gs/messaging-stomp-websocket/)

***WebSocket provides an alternative to the limitation of efficient communication between the server and the web browser by providing bi-directional, full-duplex, real-time client/server communications. The server can send data to the client at any time. Because it runs over TCP, it also provides a low-latency low-level communication and reduces the overhead of each message.***

- WebSocket is a thin, lightweight layer above TCP. This makes it suitable for using “subprotocols” to embed messages.
- we use STOMP messaging with Spring to create an interactive web application.
- STOMP (Streaming Text Oriented Messaging Protocol) is a subprotocol operating on top of the lower-level WebSocket.

### The guide

***You will build a server that accepts a message that carries a user’s name. In response, the server will push a greeting into a queue to which the client is subscribed.***

1. visit the [Spring Initializr](https://start.spring.io/#!type=maven-project&language=java&platformVersion=2.4.3.RELEASE&packaging=jar&jvmVersion=1.8&groupId=com.example&artifactId=messaging-stomp-websocket&name=messaging-stomp-websocket&description=Demo%20project%20for%20Spring%20Boot&packageName=com.example.messaging-stomp-websocket&dependencies=websocket) to generate a new project with the required dependency (Websocket).
2. Create a Resource Representation Class
   1. create your STOMP message service. The service will accept messages that contain a name in a STOMP message whose body is a JSON object.
   2. To model the message that carries the name, you can create a plain old Java object with a name property and a corresponding `getName()` method.
   3. the service will process it by creating a greeting and publishing that greeting on a separate queue to which the client is subscribed. The greeting will also be a JSON object.
   4. To model the greeting representation, add another plain old Java object with a content property and a corresponding `getContent() `method.
   5. Spring will use the Jackson JSON library to automatically marshal instances of type Greeting into JSON.

      ```java
      package com.example.messagingstompwebsocket;

      public class HelloMessage {

      private String name;

      public HelloMessage() {
      }

      public HelloMessage(String name) {
         this.name = name;
      }

      public String getName() {
         return name;
      }

      public void setName(String name) {
         this.name = name;
      }
      }
      ```

      ```java
      package com.example.messagingstompwebsocket;

      public class Greeting {

      private String content;

      public Greeting() {
      }

      public Greeting(String content) {
         this.content = content;
      }

      public String getContent() {
         return content;
      }

      }
      ```

3. Create a Message-handling Controller
      1. STOMP messages can be routed to @Controller classes.
      2. The `@MessageMapping` annotation ensures that, if a message is sent to the` /hello` destination, the `greeting()` method is called.
      3. The return value is broadcast to all subscribers of /topic/greetings, as specified in the `@SendTo`annotation.
4. Configure Spring for STOMP messaging
   1. configure Spring to enable WebSocket and STOMP messaging.
   2. Create a Java class named `WebSocketConfig`
   3. WebSocketConfig is annotated with `@Configuration` to indicate that it is a Spring configuration class.
   4. It is also annotated with `@EnableWebSocketMessageBroker`. As its name suggests, `@EnableWebSocketMessageBroker` enables WebSocket message handling, backed by a message broker.
5. Create a Browser Client
   1. With the server-side pieces in place, you can turn your attention to the JavaScript client that will send messages to and receive messages from the server side.
   2. Create an `index.html`, This HTML file imports the SockJS and STOMP javascript libraries that will be used to communicate with our server through STOMP over websocket. We also import `app.js`, which contains the logic of our client application.
   3. The `connect()` function uses SockJS and stomp.js to open a connection
   4. the `sendName()` function retrieves the name entered by the user and uses the STOMP client to send
6. Make the Application Executable
   1. Spring Boot creates an application class for you, You can use it to run this application.
   2. @SpringBootApplication is a convenience annotation that adds all of the following:
      - `@Configuration` Tags the class as a source of bean definitions for the application context.
      - `@EnableAutoConfiguration`: Tells Spring Boot to start adding beans based on classpath settings, other beans, and various property settings.
      - `@ComponentScan`: Tells Spring to look for other components, configurations, and services in the com/example package, letting it find the controllers.
   3. The `main()` method uses Spring Boot’s `SpringApplication.run()` method to launch an application. 
7. Build an executable JAR
   - You can run the application from the command line with Gradle or Maven `./gradlew bootRun`. You can also build a single executable JAR file that contains all the necessary dependencies, classes, and resources and run that ` ./gradlew build`.
8. Test the service
   1. Now that the service is running, point your browser at `http://localhost:8080` and click the Connect button.


