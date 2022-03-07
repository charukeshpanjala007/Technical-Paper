# Design Patterns

> ## Introduction
Design Pattern is a widely acknowledged concept in the software engineering industry in terms of the benefits it brings to areas of code-reuse and maintainability. As a software developer, you likely stumble upon this term at one point. Unsurprisingly, without even knowing it, the chances are that you might have already implemented them somewhere in the development journey.

A **design pattern** is used to identify reusable solutions that can be applied to recurring problems that software developers commonly face during software design. They represent time-tested solutions and best practices adopted by object-oriented software developers over time.

> ## What is a Design Pattern?
Design pattern can be considered pre-made blueprint applied to solve a particular design problem. It is not a finished piece of code that can be directly applied to your program. But rather, it is more like a template or description that can give you an idea of approaching a problem and inspiring solutions. Hence, the code for the two separate programming scenarios, implementing the same pattern can be different.

> ## Structure of a Design Pattern

Term |Description
------|-----------
**Intent**|Describes what the pattern does – the problem and the solution.
**Motivation**|Further explains the problem and how the pattern solves that problem.
**Structure**|Set of diagrams of the classes and objects that depict  parts of the pattern and how they are related
**Code**|Example in any popular language for a better grasp of the idea

> ## Why Patterns?
### &emsp;1.Avoid reinventing the wheel:
    Most of the frequently faced design problems already have a well-defined solution that is associated with a pattern. Patterns are proven solutions that can speed up development.

### &emsp;2. Codebase Maintenance:
    Patterns help in implementing DRY(Do not Repeat Yourself) – the concept which helps to prevent your codebase from growing large and unwieldy.

### &emsp;3. Easily reused:
    Reusing patterns assists in preventing minor subtle issues that can cause major problems in the application development process. This also improves code readability for coders and architects familiar with the patterns.

### &emsp;4. Enables efficient communication:
    Patterns add to a developer’s vocabulary. This allows developers to communicate using well-known, well-understood names for software interactions, making communication faster.

### &emsp;5. Improve your object-oriented skills:
    Now even if you never encounter any of these problems, learning patterns can give you insights into various approaches to solving problems using object-oriented principles.

> ## Categories of Design Pattern
Based on intent, the JavaScript design pattern can be categorized into 3 major groups:

### &emsp; a) Creational Design Pattern
    These patterns focus on handling object creation mechanisms. A basic object creation approach in a program can lead to an added complexity. Creational JS design patterns aim to solve this problem by controlling the creation process.
    Few patterns that fall under this category are – Constructor, Factory, Prototype, Singleton, etc.

### &emsp;b) Structural Design Patterns
    These patterns are concerned with object composition. They explain simple ways to assemble objects and classes into larger structures. They help ensure that when one part of a system changes, the entire structure of the system doesn’t need to do the same, keeping them flexible and efficient.
    Few patterns that fall under this category are – Module, Decorator, Facade, Adapter, Proxy, etc.

### &emsp;c) Behavioral Design Patterns
    These patterns focus on improving the communication and assignment of responsibilities between dissimilar objects in a system.
    Few patterns that fall under this category are – Chain of Responsibility, Command, Observer, Iterator, Strategy, Template, etc.

![design patterns](https://res.cloudinary.com/devvekh18/image/upload/v1646688628/technical%20paper/designpatterns_nixep9.png)


># Creational Design Patterns

## 1. Constructor Pattern
The constructor pattern is one of the most simple, popular, and modern JS design patterns. As suggested by the name, the purpose of this pattern is to aid constructor creation.

### Example:
n the below code, we have defined a function/class Person with attributes name and age.

The getDetails() method will print the name and age of the person in the format – \
“Name is age years old!” \
The syntax is given in 2 formats –  \
(a) traditional function-based syntax and \
(b) EC6 class syntax. \
Then, we instantiate an object for the class Person by invoking the constructor method using the new keyword and passing respective attribute values.

![Construstor Design Patter](https://res.cloudinary.com/devvekh18/image/upload/v1646688985/technical%20paper/constructorpattern_wg9qmi.png)

## 2. Singleton Pattern
The singleton pattern is a creational JavaScript design pattern that restricts the instantiation of a class to a single object. It creates a new instance of the class if one doesn’t exist and if existing already, it simply returns a reference to it. It is also known as the Strict Pattern.

A singleton pattern solves two problems at the same time, violating the Single Responsibility Principle.

- Guarantees that there is only a single instance of a class.
- Provide a global access point to this instance.

![Singleton Pattern](https://res.cloudinary.com/devvekh18/image/upload/v1646689566/technical%20paper/singleton_img1_hdipje.png)

A practical example would be a single database object shared by different parts of the program. There is no need to create a new instance of a database when one is already existing.

One drawback of the pattern is the difficulty associated with testing. There are hidden dependencies objects, which are difficult to single out to test.

### Example:
![singleton](https://res.cloudinary.com/devvekh18/image/upload/v1646689670/technical%20paper/singleton_img2_be1qme.png)

# Behavioural Design Pattern

## 1. Chain of Responsibility Pattern

This is a behavioral JavaScript design pattern that creates a chain of receiver objects for a request. This pattern promotes loose coupling. We can avoid coupling the sender of a request to a receiver, and more than one receiver can handle the request.

The receiving objects will be linked together, and they can choose to act on the request and/or pass it to the next receiver object. It is also easy to add new receiver objects to the chain.

Event Handling in DOM is one implementation of the Chain of Responsibility pattern.

Once an event is fired, it propagates through the DOM hierarchy, calling every event handler it runs into until it finds the appropriate “event listener” and then acts on it.

### Example:

Let us consider the scenario of an ATM. When we request an amount for withdrawal, the machine processes the request and dispends the amount as combinations of available note denominations ($100, $50, $20, $10, $5, $1).

![atm](https://res.cloudinary.com/devvekh18/image/upload/v1646689952/technical%20paper/chainofresponsibility1_ca70jp.png)

In this code on requesting an amount, a Request object is created. This object then invokes a series of get calls, which are chained together, each one handling a particular denomination. Finally, the user receives the amount as a note combination which satisfies the amount value.

![chain of resposibility](https://res.cloudinary.com/devvekh18/image/upload/v1646690068/technical%20paper/chainofresponsibility2_akhsll.png)

## 2. Iterator Pattern

The Iterator Pattern lets you access and traverses through elements of an aggregate object (collection) sequentially without exposing its underlying representation. This pattern allows JavaScript developers to design looping constructs that are far more flexible and sophisticated. In ES6, Iterator and Generators are introduced, which further aids in the Iteration pattern implementation.

### Example:

This is a simple straight-forward code for front-to-back iteration. We have defined two methods for the Iterator – hasNext() and next().

![iterator](https://res.cloudinary.com/devvekh18/image/upload/v1646690289/technical%20paper/iterator_cctyux.png)


# Structural Design Patterns

## 1. Module Pattern
Module Pattern is another prevalent JavaScript design pattern for keeping our code clean, separated, and organized. A module is a piece of self-contained code that can be updated without affecting other components. As the concept of access modifier is not supported in JavaScript, the modules help in mimicking the behavior of private/public access hence providing encapsulation.

The typical code structure will be like this:

### Example:

Here we have the flexibility of renaming like we have renamed addAnimal to add. A point to be noted is that we can’t invoke removeAnimal from an outside environment as it is dependent on the private property container.

![module pattern](https://res.cloudinary.com/devvekh18/image/upload/v1646690735/technical%20paper/modulepattern2_l8g1qk.png)
![module pattern](https://res.cloudinary.com/devvekh18/image/upload/v1646690835/technical%20paper/modulepattern3_y9k2tx.png)

># References
- https://www.youtube.com/watch?v=qJZ04KSo5Ws
- https://codesource.io/javascript-design-patterns/
- https://medium.com/@olufotebig/the-constructor-pattern-learning-javascript-design-patterns-18c2e76ae52
- https://www.educative.io/collection/page/5429798910296064/5725579815944192/4890148815765504
- https://www.educative.io/collection/page/5429798910296064/5725579815944192/5927001794805760
- https://www.sourcecodeexamples.net/2020/08/typescript-chain-of-responsibility.html
- https://www.digitalocean.com/community/conceptual_articles/module-design-pattern-in-javascript
- https://www.dofactory.com/javascript/design-patterns/iterator
- https://www.patterns.dev/posts/classic-design-patterns/