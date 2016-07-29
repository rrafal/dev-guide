# Software Design Pattern

A design pattern is a solution to a common problem in software engineering. Problem comes first,
solution is second. In other words, pattern should not be used if problem does not exist.

The most common software patterns are listed. Short explenation is provided, short enough to
fit on an index card.

## Creational

### Builder

Creating an object is difficult. It might require looking at runtime information, creating depencies,
error checking, adding decorators, etc. Write a function which creates objects of a given type.

### Abstract Factory

You need to create similar objects. Write a factor function which returns an object, where type is
determined at runtime. For example, you need to create GUI elements based on runtime environment.
Write a function which takes in a name (ex. "button") and configuration, returning correct objects.

### Dependency Injection

My class or function depends on an object, but that object is not always the same. Instead of creating
or finding the dependencies, accept them as parameters. For example, `CheckoutService` depends on
`CustomerRegistry`. We might use different `CustomerRegistry` during testing. Accept `CustomerRegistry`
as an argument to constructor in `CheckoutService`.

### Lazy Loading

Creating an object is expensive and that object is not always needed. Instead of creating it immediately,
wait until it is used. In the meantime, pass along a proxy. The proxy will create a concrete instance when
its method is called.

For example, do not create database connection until the first query is executed.

### Singleton

You need a single instance of an object. Create a factory function which keeps an instance of the object
and always returns the same copy.

This is frequently an antipattern, where singleton object becomes de-facto global variable and dependency.
It's often better to use depency injection pattern.

## Structural

### Adapter

When an implementation has incompatible interface, create an adapter class to encapsulate
the implementation. For example, if you have a legacy system which does not implement correct
interface, create adapter class that has correct interface and calls the legacy code.

### Bridge

When you have multiple implementations, seperate abstraction, allow implementations to be interchanged.
For example, having multiple graphic librararies and one or more graphic application, create common interface
IGraphicLibrary, allowing any libarary to be be used by the application. Application is the abstraction
and library is the implementation.

Adapter pattern is often needed in order to get all implementations to adopt the same abstraction.

### Composite

When having a tree structure of various objects, create a common interface for all of them. For example,
if you have jobs, tasks, and subtasks, have "status", "start" and "stop" methods on all of them. Stopping
a job stops all tasks and subtasks under that job.

### Decorator

When you need to add behavior to an object at runtime, create a decorator class. For example,
you might have multiple classes called `Service`. You might want to add logging and/or monitoring
behavior so some of them, based on runtime information. Create `ServiceLogging` and `ServiceMonitoring`
classes and have them extend `ServiceDecorator` class. Use "facetory pattern" to generate decorated
objects.

### Facade

If you have a complicated API, hide it behind a simple interface. For example, instead of making HTTP calls
to a remote API, create a class with simple methods matching your domain language.

### Proxy

When you need to intercept calls to concrete object, create proxy. Proxy has the same interface; it can be used
instead of concrete object. Proxy might do caching, logging, input validation, forward call across network, etc.

