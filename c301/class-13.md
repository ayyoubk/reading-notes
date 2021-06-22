# CRUD

## [Status Codes Based On REST Methods](https://www.moesif.com/blog/technical/api-design/Which-HTTP-Status-Code-To-Use-For-Every-CRUD-App/)

***A status code is a number **higher than 100** and **smaller than 600** that is part of a HTTP response.***

- The first digit defines the class of the status.
- A status code comes with a reason phrase.
- The code is for programmatic recognition the phrase is for humans to understand what happened.

1. In your own words, describe what each group of status code represents:

   - 100’s = informational status codes;
   - 200’s = success codes, the request met all validation requirements at the time of sending.
   - 300’s = redirection codes, the resource they are requesting isn’t available at the expected location anymore
   - 400’s = client error codes, They are all about invalid requests a client sent to a server
   - 500’s = server error codes. overwhelmed servers or unreachable servers behind proxies, but sometimes they can be directly related to client requests that trigger error exceptions on the server

1. What is a status code 202?

   - the request was valid, but its processing will finish sometime in the future. The response body should include an URL to the finished resource with some information about when it will be available, or an URL to some monitoring endpoint that tells the client when the resource is available.

1. What is a status code 308?

   - This tells the client to use another URL to access the resource and not use the current URL anymore

1. What code would you use if an update didn’t return data to a client?

   - 204 No Content

1. What code would you use if a resource used to exist but no longer does?

   - 410 Gone

1. What is the ‘Forbidden’ status code?
   - 403 Forbidden

## [Build A REST API With Node.js, Express, & MongoDB - Quick](https://www.youtube.com/watch?v=fgTGADljAeg&t=3s)

1. Why do we need to pull our MongoDB database string out of our server and put it into our .env?

   - because when we deploy the server we have to change it to another MongoDB database

1. What is middleware?

   - are functions that execute during the lifecycle of a request to the Express server. Each middleware has access to the HTTP request and response for each route (or path) it's attached to.

1. What does app.use(express.json()) do?

   - allows you to use request body and include key-value pairs of data.

1. What does the /:id mean in a route?

   - it means that it is a parameter and you can access it by using req.params

1. What is the difference beween PUT and PATCH?

   - PUT: to update all of the object
   - PATCH: to update only what you want to update

1. How do you make a defalut value in a schema?

   - by adding a defalut key when defining the value

1. What does a 500 error status code mean?

   - server error codes. overwhelmed servers or unreachable servers behind proxies, but sometimes they can be directly related to client requests that trigger error exceptions on the server

1. What is the difference between a status 200 and a status 201?
   - 201: means successfully created object and it is used with PUT and PATCH
   - 200: means everything was successfull
