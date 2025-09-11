

Every software system provides two different values to the stakeholders:
behavior and structure.


“The first value of software is its behavior. Programmers are hired to make
machines behave in a way that makes or saves money for the stakeholders.”


SOLID

Single Responsibility Principle
Open Closed Principle
Liskov Substitution Principle
Interface Segregation Principle
Dependency Inversion Principle

The chapters that follow describe each principle more thoroughly. Here is the executive summary: 

• SRP: The Single Responsibility Principle An active corollary to Conway’s law: The best structure for a software system is heavily influenced by the social structure of the organization that uses it so that each software module has one, and only one, reason to change. 

• OCP: The Open-Closed Principle Bertrand Meyer made this principle famous in the 1980s. The gist is that for software systems to be easy to change, they must be designed to allow the behavior of those systems to be changed by adding new code, rather than changing existing code. 
• LSP: The Liskov Substitution Principle Barbara Liskov’s famous definition of subtypes, from 1988. In short, this principle says that to build software systems from interchangeable parts, those parts must adhere to a contract that allows those parts to be substituted one for another. 
• ISP: The Interface Segregation Principle This principle advises software designers to avoid depending on things that they don’t use. 
• DIP: The Dependency Inversion Principle The code that implements high-level policy should not depend on the code that implements low-level details. Rather, details should depend on policies.

These principles have been described in detail in many different publications1 over the years. The chapters that follow will focus on the architectural implications of these principles instead of repeating those detailed discussions. If you are not already familiar with these principles, what follows is insufficient to understand them in detail and you would be well advised to study them in the footnoted documents. 

1. For example, Agile Software Development, Principles, Patterns, and Practices, Robert C. Martin, Prentice Hall, 2002, http://www.butunclebob.com/ArticleS.UncleBob.PrinciplesOfOod, and https://en.wikipedia.org/wiki/SOLID_(object-oriented_design) (or just google SOLID). 


Component Principles

If the SOLID principles tell us how to arrange the bricks into walls and rooms, then the component principles tell us how to arrange the rooms into buildings. Large software systems, like large buildings, are built out of smaller components. 

In Part IV, we will discuss what software components are, which elements should compose them, and how they should be composed together into systems. 


Components

Component cohesion

Three principles of component cohesion
REP: The Reuse/Release Equivalence Principle
CCP: The Common Closure Principle
CRP: The Common Reuse Principle


Component Coupling

The Acyclic Dependencies Principle








page 233 Crossing Boundaries

page 239 The Humble Object Pattern


page 278 Desing For Testability

may 10 2025
-  investigate about the Fragile Test Problem 


The solution is to design for testability. The first rule of software design—
whether for testability or for any other reason—is always the same: Don’t
depend on volatile things. GUIs are volatile. Test suites that operate the
system through the GUI must be fragile. Therefore design the system, and the
tests, so that business rules can be tested without using the GUI.



page 291 




These principles
encourage separation of concerns, programming to interfaces, and
substitutability.

The idea of a layered architecture is built on the idea of programming to
interfaces. When one module interacts with another though an interface, you
can substitute one service provider for another.


page 322

When faced with a framework, try not to marry it right away. See if there
aren’t ways to date it for a while before you take the plunge. Keep the
framework behind an architectural boundary if at all possible, for as long
as possible. Perhaps you can find a way to get the milk without buying
the cow.


page 331

Let’s put the Clean Architecture to one side for a
moment and look at a number of approaches to design and code organization. 

Package By Layer

Package By Feature

Ports and Adapters

As Uncle Bob has said, approaches such as “ports and adapters,” the
“hexagonal architecture,” “boundaries, controllers, entities,” and so on
aim to create architectures where business/domain-focused code is
independent and separate from the technical implementation details such as
frameworks and databases. To summarize, you often see such code bases
being composed of an “inside” (domain) and an “outside” (infrastructure),
as suggested in Figure 34.3.


![A code base with an inside and an outside](/images/figure_34_3.png)

The “inside” region contains all of the domain concepts, whereas the
“outside” region contains the interactions with the outside world (e.g., UIs,
databases, third-party integrations). The major rule here is that the “outside”
depends on the “inside”—never the other way around. Figure 34.4 shows a
version of how the “view orders” use case might be implemented.





page 339

What we need here is a guideline—an architectural principle—that says
something like, “Web controllers should never access repositories directly.”
The question, of course, is enforcement. Many teams I’ve met simply say, “We
enforce this principle through good discipline and code reviews, because we 
trust our developers.” This confidence is great to hear, but we all know what
happens when budgets and deadlines start looming ever closer.




Package By Component

A key benefit of the “package by component” approach is that if you’re
writing code that needs to do something with orders, there’s just one place
to go—the OrdersComponent. Inside the component, the separation of
concerns is still maintained, so the business logic is separate from data
persistence, but that’s a component implementation detail that consumers
don’t need to know about. This is akin to what you might end up with if you
adopted a micro-services or Service-Oriented Architecture—a separate
OrdersService that encapsulates everything related to handling orders. The
key difference is the decoupling mode. You can think of well-defined
components in a monolithic application as being a stepping stone to a microservices architecture. 


page 345 
It 's explain about access modifiers for use on packages, with some examples of diferent architectural styles






Conclusion: The Missing Advice

The whole point of this chapter is to highlight that your best design
intentions can be destroyed in a flash if you don’t consider the intricacies of
the implementation strategy. Think about how to map your desired design
on to code structures, how to organize that code, and which decoupling
modes to apply during runtime and compile-time. Leave options open where
applicable, but be pragmatic, and take into consideration the size of your
team, their skill level, and the complexity of the solution in conjunction with
your time and budgetary constraints. Also think about using your compiler to
help you enforce your chosen architectural style, and watch out for coupling
in other areas, such as data models. The devil is in the implementation
details.



page 352

