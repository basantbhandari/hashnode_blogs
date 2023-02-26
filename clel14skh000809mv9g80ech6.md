# difference between abstract class and interface

In object-oriented programming, both abstract classes and interfaces are used to define contracts that classes must follow, but there are some key differences between them. Here are the main differences between abstract classes and interfaces:

1. Definition: An abstract class is a class that cannot be instantiated and is intended to be subclassed by other classes. An interface is a collection of abstract methods that must be implemented by a class.
    
2. Implementation: An abstract class can contain both abstract and non-abstract methods, and can also have variables, constructors, and static methods. A class that implements an interface must implement all the methods declared in the interface, but cannot contain any implementation details.
    
3. Inheritance: A class can only inherit from one abstract class, but it can implement multiple interfaces.
    
4. Access Modifiers: An abstract class can have access modifiers on its constructors and methods, while all methods of an interface are implicitly public.
    
5. Type of Relationship: Abstract classes are used when a relationship is more of an "is-a" relationship, while interfaces are used when a relationship is more of a "has-a" or "can-do" relationship.
    

In summary, abstract classes are used to define a common behavior among a group of related classes and can provide implementation details, while interfaces define a contract that classes must implement without providing implementation details.