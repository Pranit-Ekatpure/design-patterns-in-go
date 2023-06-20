# Design Patterns in GO
## SOLID Design Principles
### 1. Single Responsibility Principle (SRP)
There should never be more than one reason for a class to change. In other words, every class should have only one responsibility.
### 2. Open-Closed Principle (OCP)
Software entities ... should be open for extension, but closed for modification.
### 3. Liskov Substitution Principle (LSP)
Functions that use pointers or references to base classes must be able to use objects of derived classes without knowing it.
### 4. Interface Segregation Principle (ISP)
Clients should not be forced to depend upon interfaces that they do not use.
### 5. Dependency Inversion Principle (DIP)
Depend upon abstractions, [not] concretions.
High-level modules should not import anything from low-level modules. Both should depend on abstractions (e.g., interfaces).
Abstractions should not depend on details. Details (concrete implementations) should depend on abstractions.

## Design Patterns
## 1. Creational Patterns 
> Singleton, Builder, Factory, Prototype, and Abstract Factory Design Patterns
 

Creational design pattern, as the name implies, groups common practices for creating objects, so object creation is more encapsulated from the users that need those objects. Creational patterns try to give read-to-use objects to users instead of asking for their creation , which in some cases, could be complex, or which would couple your code with the concrete implementations of the functionality that should be defined in an interface.


### Singleton design pattern:
> Having a unique instance of a type in the entire program

It provides the single instance of an object, and gaurantee that there are no duplicates. At the first call to use the instance, it is created and then resused beteween all the parts in the application that need to use that particular behavior.

Use case examples:
* To use the same connection to a database to make every query
* To open a secure shell (SSH) connection to a server to do a few tasks, and don't want to reopen the connection for each task.
* To limit the access to some variable or space, use a singleton as the door to this variable
* To limit the number of calls to some places, create a singleton instance to make the calls in the accepted window.

### Builder design pattern:
> Reusing an algorithm to create many implementations of an interface. The intent of the builder design pattern is to separate the construction of a complex object from its representation.

The builder pattern helps us construct complex objects without directly instantiating their struct, or writing the logic they require. An object that could have dozens of fields that are more complex structs themselves and there could be many onjects with these characteristics. We don't want to write the logic to create all these objects in the package that just needs to use the objects.

A builder design pattern tries to:
* Abstract complex creations so that creation is separated from the object user
* Create an object step by step filling its fields and creating the embdded objects
* Reuse the object creation algorithm between many objects

### Factory design pattern:
> Factory, a component resposible soley for the wholesale (not piecewise, unlike builder) creation of objects. With the Factory method, we delegate the creation of families of objects to a different package or object to abstract us from the knowledge of the pool of possible objects we could use.

Objectives:
* Delegating the creation of new instances of structures to a different part of the
program
* Working at the interface level instead of with concrete implementations
* Grouping families of objects to obtain a family object creator

### Prototype design pattern:
> The aim of the Prototype pattern is to have an object or a set of objects that is already created at compilation time, but which you can clone as many times as you want at runtime.

Objectives:
* The main objective for the Prototype design pattern is to avoid repetitive object creation. Imagine a default object composed of dozens of fields and embedded types. We don't want to write everything needed by this type every time that we use the object, especially if we can mess it up by creating instances with different foundations: Maintain a set of objects that will be cloned to create new instances, Provide a default value of some type to start working on top of it, Free CPU of complex object initialization to take more memory resources.

## 2. Structural Patterns
### Adapter design pattern:
> It is one of the most commonly used structural patterns. An adapter will allow us to use something that wasn't built for a spcefic task at the beginning. The Adapter pattern is very useful when, for example, an interface gets outdated and it's
not possible to replace it easily or fast. Instead, you create a new interface to deal with the current needs of your application, which, under the hood, uses implementations of the old interface. Adapter also helps us to maintain the open/closed principle in our apps, making them more predictable too. They also allow us to write code which uses some base that we can't modify.

Objectives:
* The Adapter design pattern helps to fit the needs of two parts of the code that are incompatible at first. 

### Bridge design pattern:
> The Bridge pattern tries to decouple things as usual with design patterns. It decouples abstraction (an object) from its implementation (the thing that the object does). This way, we can change what an object does as much as we want. It also allows us to change the abstracted object while reusing the same implementation.

Objectives:
> The objective of the Bridge pattern is to bring flexibility to a struct that change often. Knowing the inputs and outputs of a method, it allows us to change code without knowing too much about it and leaving the freedom for both sides to be modified more easily.

### Composite design pattern:
> In the Composite design pattern, you will create hierarchies and trees of objects. Objects have different objects with their own fields and methods inside them. This approach is very powerful and solves many problems of inheritance and multiple inheritances.

Objectives:
> The objective of the composition is to avoid hierarchy where the complexity of an application could grow too much, and the
clarity of the code is affected. Use this pattern when the composite and individual object form a tree-like structure.