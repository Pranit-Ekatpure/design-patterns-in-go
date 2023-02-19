# go-design-patterns
## Creational Patterns - Singleton, Builder, Factory, Prototype, and Abstract Factory Design Patterns
 
```
Creational design pattern, as the name implies, groups common practices for creating objects, so object creation is more encapsulated from the users that need those objects. Creational patterns try to give read-to-use objects to users instead of asking for their creation , which in some cases, could be complex, or which would couple your code with the concrete implementations of the functionality that should be defined in an interface.
```

* Singleton design pattern
> Having a unique instance of a type in the entire program

```
It provides the single instance of an object, and gaurantee that there are no duplicates. At the first call to use the instance, it is created and then resused beteween all the parts in the application that need to use that particular behavior.
Use case examples:
    - To use the same connection to a database to make every query
    - To open a secure shell (SSH) connection to a server to do a few tasks, and don't want to reopen the connection for each task.
    - To limit the access to some variable or space, use a singleton as the door to this variable
    - To limit the number of calls to some places, create a singleton instance to make the calls in the accepted window.
```