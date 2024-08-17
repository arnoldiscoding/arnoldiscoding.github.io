---
title: Introduction on Dependency Injection
date: 2024-08-17 16:11:00
categories: [concepts]
tags: [concepts,dependency injection,c#]
---
# Dependency Injection 
## What is Dependency Injection? A higher level explanation

The whole concept of dependency injection revolves around client and service. The client wants some action to be done, and tells the service to complete the action for them. 

To give a higher level example, let's you are hungry, and you are trying to get food. There are a million ways to get food: you can order food delivery, you can go to the fridge and make yourself something, or you can scream out "Mom!". However, you are so hungry that you don't care about how the food is made, or which restaurant to order, you just want it to be delivered to you. Imagine that now you have a butler that provides this service. In that case, all you need to do is to tell the butler you want food, and then food will come to you later. You don't know how the food is made or who made the food, but you get it.

Dependency Injection is similar in nature. This principle ensures that when a class is trying to use a service, they need not to know how it works, as the service is provided by some sort of external entities. The classes using the service is therefore the **clients**, the service is the **dependencies**,  and the external entities are the **injectors**. 

Note that the client is **not** creating the an instance of the injector, but rather assuming the injector has already been instantiated somewhere and are available by calling it directly. Therefore in general, you shouldn't see `new` or any keyword that hinted object creation when the service is injected.


## How is dependency injected?

There are in general two ways to inject dependencies:
1. Through Constructors
2. Through Setter Methods

### Constructors
The dependencies are usually requested in the constructor of the client, meaning that whoever is instantiating the client needs to specify the type of dependencies during instantiation. 

There is one slight problem with this approach. Since the dependencies are usually stored as `private` memebers in the client class (you can make them `public` but it is not recommended), once they are set, you cannot change it in the lifecycle of the client object.

### Setter Method
You can specify a public setter method in the client class to set the dependencies. In this case, you can change the implementation of the dependencies if needed. But make sure to double check the dependencies are actually set before you uses them.

## Inheritance vs Dependency Injection

The two might sound similar at the beginning, but they represents two different concepts. 

Inheritance can be seen as a shared identity. They are related under the Liskov Substitution Principle. Whatever the parent class can do, the child class can also do, and they can perform similar action because of this inherited relation.

Dependency Injection is a form of shared functionality. Two classes may need to perform similar actions, but they are not necessarily related, it is just a part of them needed the same feature.


