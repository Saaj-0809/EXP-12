## EXP-12

## Aim:
To study and implement Constructors and Destructors.

## Theory:
A constructor in C++ is a special member function whose name matches exactly with the class name. It is primarily used to initialize the variables of a class when an object is created. Constructors do not have a return type, not even void, and are automatically invoked when an object is instantiated. While constructors are typically defined in the public section of a class to allow easy creation of objects, they can also be declared in the private or protected sections if restricted access is desired. Constructors can be overloaded to allow multiple ways of initializing an object, but they cannot be declared as virtual functions. The syntax for a constructor is straightforward: it is defined with the class name followed by parentheses that may include parameters. A constructor can be defined either inside the class definition, like ClassName(parameters) { // implementation }, or outside the class definition using the scope resolution operator, like ClassName::ClassName(parameters) { // implementation }.





