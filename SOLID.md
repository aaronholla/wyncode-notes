# SOLID code

Better to build a lare number of small things rather than a large number of small things. Helpful for better code reuse.

## Single Responsibility Principle (SRP)
Everything should have one thing that it does

A single class should only have a single responsibility.


## Open/closed principle 
Adding new stuff shouldn't have to update existing code. Open for extention closed for modification.

You don't want to have to change the original class to add new functionality.


## Liskov substitution
Inheretence - children should behave similar to how a parent behaves.

If q(x) it true with x being type T, q(y) of type S where S is a subtype of T should also be true.

## Interface segregation principle
Do not force interfaces to implement things that don't make sense for the interface to be neccesary. 

## Dependency inversion principle
Entities must depend on abstractions not on concretions. What is it for. give broad names and implementations.

Expecting a dependency being injected into it. where it expects the actually dependency to be passed into it.

Class does not have to know what the dependency is as long as it implements what it needs to run on it.