
Higher Levels
Businesses must choose what to work on.  They typically want to choose the items with the highest marginal utility

Benefits of Software Architecture (good design)
Easier to Add to
Easier to Change
Easier to Understand
Reduce Complexity
Separate teams can implement

Cons of too much / too little architecture
iteration is good

Ownership
Who can debug
Who can add to it
Who can write the code
Error Handling / when things go wrong

APIs

Quality Attributes

Testing
What happens when many concurrent requests
What is the bottleneck
What happens when design changes
System Design to try and break

-------------

Books

Philosophy of Software Design
----
Reduce Complexity or encapsulate it
Overall Complexity is complexity of a part times how often you deal with it
- Focus on making most used path less complex
Complexity symptoms:
* Shotgun surgery
* Not even knowing where to start
* Cognitive Load*
Complexity increases slowly if you let it
Think of a few ways your design can change in the future and make sure it is easy with the design
Modules should be deep not wide, one interface instead of many, small interface for much implementation
Folks should be able to focus on the interface and not the implementation
Abstractions are great but they shouldn't hide information or give too much information
* both are bad*
Make the common case as simple as possible
Information should be hidden in implementation as much as possible (David Parnas)
Focus on General Purpose Design
* *
Who needs to know what and when
What is the simplest interface I can create
Separate needed specialization away from the General case (by pushing it up)
Try to avoid interface duplication
* Each Layer should provide a benefit and not just a shallow interface
* Don't want to click through 10 functions in stack to do one thing
* More interfaces add more complexity so too much subdividing can be bad
Make components independent
* One change in one area*
Reduce places that errors are handled
* retriable vs non-retriable
* Crucial vs not needed
* Solutions
** Define Error out of Existence (just don't throw for non important cases)
** Have Mask Exceptions
** Aggregate Exceptions
Design it twice!
Tips:
* Write comments for interface before implementation*
* Design for reading not writing
Red Flags
* Having to know interfaces behind the interface being used
* General use requires knowledge of specialized cases
* You have to understand a different component in order to understand some component
* Non-trivial code is repeated
* Hard to describe what component does
* Interface requires knowledge of implementation



----------------
Other

Lifecycle of systems (Xllora)
Common Patterns
API Supply Chains
Pareto Frontier
Architecture Decision Records
Incremental reduces risk
Mental model that folks have should match the code
Domain Driven Design?
SOLID principles

Other Books
Just enough Software Architecture
Software Architecture in practice *
Documenting Software Architures



------------
Ideas?

Category theory
Graph Theory
Computability