# Software Design Pattern

A design pattern is a solution to a common problem in software engineering. Problem comes first,
solution is second. In other words, pattern should not be used if problem does not exist.

The most common software patterns are listed. Short explenation is provided, short enough to
fit on an index card.

## Structural

### Adapter

When an implementation has poor interface, create an adapter class to encapsulate the implementation.
Interface which is poorly designed, difficault to use, or not fitting project standards should
use an adapter. For example, instead of making HTTP calls to remote API, create adapter class
with simple methods matching your domain language.

### Bridge

When you have multiple implementations, seperate abstraction, allow implementations to be interchanged.
For example, having multiple graphic librararies and one or more graphic application, create common interface
IGraphicLibrary, allowing any libarary to be be used by the application. Application is the abstraction
and library is the implementation.

