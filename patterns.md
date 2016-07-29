# Patterns

The most common software patterns with a briefly explenation. The explenation should fit
on an index card.

## Structural

### Adapter

A class encapsulates another (implementation) class and matches required interface. It's
useful when you have an implementation but it has wrong interface.

### Bridge

Seperate abstraction and implementation. For example, implement algorithm as a class,
passing in math libary to algorithm's constructor. Add a bridge between algorithm class
and library class. This allows to change library without affecting algorithm.
