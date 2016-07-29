# Software Design Pattern

A design pattern is a solution to a common problem in software engineering. Problem comes first,
solution is second. In other words, pattern should not be used if problem does not exist.

The most common software patterns are listed. Short explenation is provided, short enough to
fit on an index card.

## Structural

### Adapter

A class encapsulates another (implementation) class and matches required interface. It's
useful when you have an implementation but it has wrong interface.

### Bridge

Seperate abstraction and implementation. For example, implement algorithm as a class,
passing in math libary to algorithm's constructor. Add a bridge between algorithm class
and library class. This allows to change library without affecting algorithm.
