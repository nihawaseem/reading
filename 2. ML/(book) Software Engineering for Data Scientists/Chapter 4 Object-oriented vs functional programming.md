- frameworks for ways to break down your code 

## OOP
- an object is a thing 
- **class:** defines an object. an individual object is an instance of a class.
- **methods:** something you can do to objects of a class
- **attributes**: variables that are some property of a class (and hence object)
- e.g. The book you’re currently
reading, Software Engineering for Data Scientists, is an object of the class
“Book.” One of the attributes of this object is its number of pages and another is the
name of the author. A method you could call on this object is to “read” it. There are
many instances of the “Book” class, but they all have a certain number of pages, and
they can all be read.

### Defining your own classes
- define class with class statement
- store attributes every time a new instance of an object is initialized, using __init__
-![[Pasted image 20250612192101.png]]
![[Pasted image 20250612192124.png]]

### OOP principles
- **Inheritance**: you can extend a class by creating another class that builds on
it
- **Encapsulation**: you can only see the interface to the class, not the internal details of what's going on
- **Abstraction**: It means that you should deal with a
class at the appropriate level of detail. So you might choose to keep the details of
some calculation within a method, or you might allow it to be accessed through the
interface.
- **Polymorphism**: you can have the same interface for different classes,
which simplifies your code and reduces repetition

## Functional programming
- all about functions that don’t change
- functions are immutable, “pure,” and free of side effects
- For example, if you have a function that adds an item to a list, that function should return a new copy of the list rather than modifying the existing
list

### Applying functions to dataframes 
![[Pasted image 20250612193243.png]]