

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
 




