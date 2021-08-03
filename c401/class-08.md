# Read: 08 - OO Design

## [SOLID principles intro](https://www.digitalocean.com/community/conceptual_articles/s-o-l-i-d-the-first-five-principles-of-object-oriented-design)

SOLID is an acronym for the first five object-oriented design (OOD) principles by Robert C. Martin, it stands for:

- S - Single-responsibility Principle
- O - Open-closed Principle
- L - Liskov Substitution Principle
- I - Interface Segregation Principle
- D - Dependency Inversion Principle

1. ***Single-responsibility Principle*** that states that every module, class or function in a computer program should have responsibility over a single part of that program's functionality.
2. ***Open-Closed Principle*** that states Software entities (classes, modules, functions, etc.)  can allow its behavior to be extended without modifying its source code.
3. ***Liskov substitution principle*** that states objects of a superclass shall be replaceable with objects of its subclasses without breaking the application.
  
  - It extends the Open/Closed principle and enables you to replace objects of a parent class with objects of a subclass without breaking the application. This requires all subclasses to behave in the same way as the parent class. To achieve that, your subclasses need to follow these rules:
    - Don’t implement any stricter validation rules on input parameters than implemented by the parent class.
    - Apply at the least the same rules to all output parameters as applied by the parent class

4. ***interface-segregation principle*** states that clients should not be forced to depend upon interfaces that they do not use
5. ***Dependency Inversion Principle*** states that entities must depend on abstractions, not on concretions. It states that the high-level module must not depend on the low-level module, but they should depend on abstractions.

## [OO SOLID principles in real life](https://dzone.com/articles/the-solid-principles-in-real-life)

- If we follow these principles, we will get code that's a lot more likely to be maintainable. these design guidelines, properly followed, will tend to steer you toward writing clean code.

- In lake areas, instead of going to work using the car and boat together, you can use the amphibious vehicle. this is a good example about single responsibility principle.
  
- People shouldn't change your class later. a good example of Open-Closed Principle: in smartphones, App stores let you extend the base functionality of the phone. And by that The core phone functionality closed for modification and open to an extension .
  
- Liskov substitution principle state that any child type of a parent type should be able to stand in for that parent without things blowing up. for example : Since the cat and dog are child in the animal class, cats should meow, and dogs should bark, not the opposite.

- The interface segregation principle (isp) says that you don't want to force clients to depend on things they don't actually need. As in restaurant's menu. You'll see all the normal menu mainstays, and then something that's just called "soup of the day." Clients that don't care about the soup needn't even be concerned, and clients that do use a different interface -- asking the server.

- The dependency inversion principle (dip) encourages you to write code that depends upon abstractions rather than upon concrete details.As when going to store and pay for something with a credit card. The clerk doesn't examine your card. He just takes your card, whatever it is, and swipes it, both you and the clerk depend on the credit card abstraction without worrying about specifics.
