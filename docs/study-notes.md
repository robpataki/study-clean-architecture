# Clean Architecture Study notes

> The only way to go fast is to go well.
>
> – Robert C. Martin (Uncle Bob)

## Notes

**Speculative generality:** countless parameters, hard-coded guess work

Humans are good at operating with incomplete knowledge. We learn more by exploring and experimenting.

Good architecture is flexible, it comes from understanding it more as a journey, not a destination.

The goal of software architecture is to minimise the human resources required to build and maintain the required system.

**The signature of a mess:** when systems are thrown together in a hurry and more and more developers are added to the project without thought or care for the cleanliness of the code.

"We go live first, then we clean up" is a tell tale sign of the signature of a mess.

**Value in software to stakeholders:**

1. Behaviour (function)
2. Architecture (ease of change)

It is far more important for software to be easy to change than for it to work. If it's easy to change, it is easy to make it work.

Software architects are more focused on the structure of the system rather that the features and functions of it.

If the architecture becomes too hard to change, or change itself causes too many bugs, the cost of change will be disproportionally high compared to the added value of the feature.

## Design Principles

### SOLID

| Initial | Principle                       | Abbrebiation |
| ------- | ------------------------------- | ------------ |
| **S**   | Single Responsibility Principle | SRP          |
| **O**   | Open/Close Principle            | OCP          |
| **L**   | Liskov Substitution Principle   | LSP          |
| **I**   | Interface Segregation Principle | ISP          |
| **D**   | Dependency Inversion Principle  | DIP          |

#### Single Responsibility Principle (SRP)

A module should be responsible to ONE, and ONLY ONE actor.

#### Open/Close Principle (OCP)

A software artifact should be open for extension but closed for modification.

The goal is to make the system easy to extend without incurring a high impact of change. This goal is accomplished by partitioning the system into components, and arranging those components into a dependency hierarchy that protects higher-level components from changes in lower-level components.

#### Liskov Substitution Principle (LSP)

Functions that use pointers to base classes must be able to use objects or derived classes without knowing it.
This principle is about OOP and class inheritance.

Subclass extending superclass if used by the program interchangeably should not break the program.

**Bad example:**
Rectangle (setW, setH) != Square (setSize)

#### Interface Segregation Principle (ISP)

Clients should not be forced to depend on interfaces that they don't use.

**Example 1:**

Break up a big interface/object into multiple interfaces/objects, grouped by responsibility or concern of the consuming classes and components.

**Example 2:**

Instread of passing in a big object into a component and make it cherry pick what it needs from that object, pass in exactly what it needs and no more.

#### Dependency Inversion Principle (DIP)

High-level modules should depend on abstractions rather than concrete implementations.

**Stable abstractions > Fragile concretions**

[DIAGRAM 1]

The source code dependencies are inverted against the flow of control.

## Component Principles

The **SOLID** principles help with arranging bricks into walls and rooms. **Component Principles** help with the arrangement of the rooms into buildings.

Components are units of deployment, they are the smallest entities that can be deployed as part of a system.

**Examples:** JAR/Gem/DLL files (not so webby)

Components are independently deployable and can be developed independently.

### The 3 principles of component cohesion

| Principle                | Abbrebiation |
| ------------------------ | ------------ |
| Reuse/Release Principle  | REP          |
| Common Closure Principle | CCP          |
| Common Reuse Principle   | CRP          |

#### Reuse/Release Principle
