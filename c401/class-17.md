# Read: 17 - Spring Authorization

## [Spring Boot and OAuth2](https://spring.io/guides/tutorials/spring-boot-oauth2/)

**_OAuth 2.0 help in building an app doing various things with "social login"._**

### Single Sign On With GitHub

- follow this steps to create a minimal application that uses GitHub for authentication :

    1. create a Spring Boot application by [Spring Initializer](https://start.spring.io/)
    2. create  a home page `index.html` in the `src/main/resources/static` folder
    3. Add Spring Security OAuth 2.0 Client dependency. (Since you’re wanting to do a "social" login (delegate to GitHub), you should include the Spring Security OAuth 2.0 Client starter) `spring-boot-starter-oauth2-client` By adding this, it will secure your app with OAuth 2.0 by default
- configure your app to use GitHub as the authentication provider by:
    1. Add a New GitHub App
    2. Configure `application.yml` to make the link to GitHub

- What Just Happened?

  - This app, in OAuth 2.0 terms, is a Client Application, and it uses the authorization code grant to obtain an access token from GitHub (the Authorization Server).
  - It then uses the access token to ask GitHub for some personal details (only what you permitted it to do), including your login ID and your name. In this phase, GitHub is acting as a Resource Server, decoding the token that you send and checking if it gives the app permission to access the user’s details. If that process is successful, the app inserts the user details into the Spring Security context so that you are authenticated.

- Add a Welcome Page
    - modify the simple app you just built by adding an explicit link to login with GitHub.
    - Instead of being redirected immediately, the new link will be visible on the home page
    - the user can choose to login or to stay unauthenticated.
    - Only when the user has clicked on the link will the secure content be rendered.
    - follow this steps : 
        1. create a button to go to github login
        2. using JQuery send a request to the correct endpoint
        3. add the server-side endpoint just mentioned, calling it `/user`. It will send back the currently logged-in user

    - Making the Home Page Public
      - This app will now work fine and authenticate as before, but it’s still going to redirect before showing the page. To make the link visible, we also need to switch off the security on the home page by extending `WebSecurityConfigurerAdapter`

- Add a Logout Button
    1. On the client, we just need to provide a logout button and some JavaScript to call back to the server to ask for the authentication to be cancelled.
    2. The `logout()` function does a POST to `/logout` and then clears the dynamic content.
    3. Adding a Logout Endpoint
    4. add a filter that creates the cookie. In the `WebSecurityConfigurerAdapter`

- Login with GitHub
  - To use Google’s OAuth 2.0 authentication system for login, you must set up a project in the Google API Console to obtain OAuth 2.0 credentials.
  - supply a redirect URI by add Authorized redirect URIs field is set to `http://localhost:8080/login/oauth2/code/google`
  - configure the client to point Google, Because Spring Security is built with multiple clients in mind, you can add our Google credentials alongside the ones you created for GitHub
  - Adding the Login Link
- How to Add a Local User Database
    1. Choose a backend for your database, and set up some repositories (using Spring Data, say) for a custom User object that suits your needs and can be populated, fully or partially, from external authentication.
    2. Implement and expose OAuth2UserService to call the Authorization Server as well as your database.

