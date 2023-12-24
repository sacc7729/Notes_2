---
tags:
  - Software_Architecture
---

# References

* A Philosophy of Software Design

# Motivation

Businesses must choose the most efficient work for the resources (marginal utility).

Software Architecture helps design systems that accomplish some need.  A good software architecture makes it easy to:
* Add Functionality
* Understand the System
* Split into different work

Good software architecture reduces complexity for the programmers involved.  A complex architecture includes:
* Unnecessary mental effort to understand
* Making multiple changes in different places for a single feature
* Guesswork on where to start

# Iterations

The requirements for some software system many not be fully understood.  The software system may not fully work how stakeholders envision.

It is greatly recommended to build the software in iterations and to get feedback.  Building an entire system at once builds compounding risk.  If every assumption is 90% correct then 7 assumptions leads to a 48% of failure: $0.9 ^ 7 \approx 0.48$

# Reducing Complexity

Stakeholders (including programmers) should need to know the minimum information needed to perform some function.  Too much information will lead to more complex systems.  Too little information will lead to assumptions.

You should have a map of some sort of parameters $x_i$ to some result $y_i$.  Minimize $\sum m(x_i)$ for the most common cases, where $m$ is the information needed to be known about some parameter.

Tips on reducing complexity are:
* Design for the common case
* Require changes for some functionality to be all made in one location
* Have interfaces hide the implementation
* Require a low number of interfaces to be understood for some functionality
* Make deep modules (simple interface for much implementation)
* Reduce the total number of interfaces

# Mathematical Tips
Represent nodes as some output.  Have a directed graph when an input is required for the node.  Reduce the number of nodes that all need to be colored to point to a specific node.

# APIs

Some general tips for APIs (especially protos):

* Precisely and concisely document fields
* Use different messages for wire and storage
* For mutations support partial updates
* Don't include primatives in top level requests
* Use string for an ID
* Include a field read mask
* Prefer idempotency
* Propagate status code carefully


# Ownership

Split up components so that ownership belongs to the correct team.  Things that may be owned are:
* Ability to debug the system
* Ability to add code to the system
* Ability to approve code changes to the system
* Responsibility for dealing with failures
* Responsibility for client communication
* Responsibility for client integrations

# Quality Attributes

Determine which quality attributes are most useful (e.g. security, reliability, availability) when making trade-offs.

# Tips

* Design it twice
* Make sure the design works for future changes
* Make the default simple
* Design for reading code and not writing code
* Write comments first.  Everything should be able to be understood without knowing the implementation.

# Red Flags

Some common red flags:

* Having to know the implementation hidden behind the interface
* General use requires knowledge of specialized areas
* One change requires modifying many areas
* Hard to describe what a component does
* You have to learn about multiple components together

# Testing

What is the bottleneck?
Can you war game to break the design?
What happens when there are many concurrent requests?
