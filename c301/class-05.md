# Thinking in React

***React is, in our opinion, the premier way to build big, fast Web apps with JavaScript. It has scaled very well for us at Facebook and Instagram.***

![thinking in react](https://miro.medium.com/max/1705/1*Dee4cg5Hzg7JME1A9tjZJQ.png)

*One of the many great parts of React is how it makes you think about apps as you build them. In this document, we’ll walk you through the thought process of building a searchable product data table using React.*

1- How would you break a mock into a component heirarchy?

- by devide the mock into subcomponents

2- What is the single responsibility principle and how does it apply to components?

- a component should ideally only do one thing. 
- by divide our work into componentsand subcomponents


3- Build A Static Version in React

- To build a static version of your app that renders your data model, you’ll want to build components that reuse other components and pass data using props. props are a way of passing data from parent to child. If you’re familiar with the concept of state, don’t use state at all to build this static version. State is reserved only for interactivity, that is, data that changes over time. Since this is a static version of the app, you don’t need it.

4- Once you have a static application, what do you need to add?

-  make the website interactive by adding state

5- What are the three questions you can ask to determine if something is state?

- Is it passed in from a parent via props?
- Does it remain unchanged over time? 
- Can you compute it based on any other state or props in your component?

6- How can you identify where state needs to live?

- Identify every component that renders something based on that state. 