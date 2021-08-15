# Read: 16 - Spring Authentication

## [Spring Security overview](https://spring.io/guides/topicals/spring-security-architecture/)

### Authentication and Access Control

#### Authentication : To determine if a user is authenticated.

The main strategy interface for authentication is `AuthenticationManager`, which has only one method:

```java
public interface AuthenticationManager {

  Authentication authenticate(Authentication authentication)
    throws AuthenticationException;
}
```

- An AuthenticationManager can do one of 3 things in its `authenticate()` method:

    - Return an Authentication (normally with `authenticated=true`) if it can verify that the input represents a valid principal.

    - Throw an `AuthenticationException` if it believes that the input represents an invalid principal.

    - Return `null` if it cannot decide.

- The most commonly used implementation of AuthenticationManager is ProviderManager, which delegates to a chain of AuthenticationProvider instances.
- An AuthenticationProvider is a bit like an AuthenticationManager, but it has an extra method to allow the caller to query whether it supports a given Authentication type:

    ```java
    public interface AuthenticationProvider {

        Authentication authenticate(Authentication authentication)
                throws AuthenticationException;

        boolean supports(Class<?> authentication);
    }
    ```
***An AuthenticationManager hierarchy using ProviderManager***
![ProviderManager](https://github.com/spring-guides/top-spring-security-architecture/raw/main/images/authentication.png)

#### Customizing Authentication Managers

- Spring Security provides some configuration helpers to quickly get common authentication manager features set up in your application
- The most commonly used helper is the `AuthenticationManagerBuilder`.

### Authorization or Access Control

- Authorization : What an authenticated user is allowed to do.
- After authentication is done successfully authorization can be done after that.
- the core strategy here is `AccessDecisionManager`
- An `AccessDecisionVoter` considers an Authentication (representing a principal) and a secure `Object`, which has been decorated with `ConfigAttributes`
- `Object` represents anything that a user might want to access (a web resource or a method in a Java class are the two most common cases).
- Most people use the default `AccessDecisionManager`, which is `AffirmativeBased`
- It is very common to use `ConfigAttributes` that are Spring Expression Language (SpEL) expressions — for example, `isFullyAuthenticated() && hasRole('user')`.

### Web Security

- Spring Security in the web tier (for UIs and HTTP back ends) is based on Servlet Filters
- The process can be illustrated in chaining a number of ordered filters that is applied to a request until it reaches a client or server.
- `FiltersChainProxy` is the first filter implemented with spring security.
- The security filters are `@Beans` in the ApplicationContext.
- `FilterChainProxy` is the parent of all implemented filters.
- By extending configure method from `WebSecurityConfigurerAdapeter` and the class that holds it can be annotated with the `@Order` annotation to give a priority to each secured class.
- Request matchers are configurations used to apply security to a specific HTTP requests.
- Securing a method is that the user have to go through security authentications to execute the method using the secured annotations.

![Web Security](https://github.com/spring-guides/top-spring-security-architecture/raw/main/images/filters.png)

## [Spring Auth Cheat Sheet](https://github.com/codefellows/seattle-java-401d2/blob/master/SpringAuthCheatSheet.md)