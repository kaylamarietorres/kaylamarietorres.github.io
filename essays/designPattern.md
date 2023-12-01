---
layout: essay
type: essay
title: "Design Patterns -change tite"
# All dates must be YYYY-MM-DD format!
date: 2023-11-26
published: false 
labels:
  - Artificial Intelligence
  - Chat GPT
  - Questions & Answers
---
<img class="center" src="../img/artificialIntelligence/header.png">

## What are design patterns

Design patterns in Computer Science can be thought of as proven solutions to common problems that programmers face when designing software. 

Imagine you are building a house. When architects design houses, they often follow certain patterns or blueprints that work well for different scenarios. For example, they might use a particular layout for the rooms, standard techniques for plumbing and electrical wiring, or common designs for windows and doors. 

Similarly, in Computer Science, design patterns are like those proven blueprints or templates for solving specific problems in software development. They're not actual lines of code but rather general solutions that can be applied to different situations. These patterns help programmers to create more efficient, reusable, and maintainable code by providing them with tested methods for solving recurring problems.

## How have I used them in my code

#### Singleton
The singleton design pattern can be described as a "global variable". We have a class, and we ensure that only a single instance of that class can exist. It helps centralize the access point to that resource and prevents unnecessary duplication. However, while Singletons can be handy, they should be used judiciously because they can also introduce potential issues, such as making code harder to test or creating dependencies that are hard to trace.

#### MVC 

The Model-View-Controller (MVC) design pattern is a way of organizing and structuring software applications, especially those with a user interface.
Imagine you are building a system like a music player app. In the MVC pattern, the *model* 
- Observer
- Factory

The factory design pattern consists of creating objects without exposing underlying logic, potentially returning objects associated with different classes and/or creating dependent objects. Factory 

- Publish-subscribe
- Prototype
- Front Controller 

patterns help newbies acquire the hard-won experience of ninjas

--Make italic for the quote

[A design pattern] "describes a problem that occurs over and over again in our environment, and then describes the core of the solution to the problem, in such a way that you can use this solution a million times over, without ever doing it the same way twice" -Christopber Alexander, 1977

Design patterns help move software development forward as a discipline through establishing a standard of good practices and solutions to problems faced by previous developers. Also known as commonly occuring problems, design patterns offer a template to use in different situations. 

The purpose of design patterns are to allow new people to the field obtain the experiences obtained through the trial and error of their predecessors.


The standard of describing a design pattern are as follows: 


- Name
  - Meaningful descriptor
- Problem description
  - when to apply the pattern
- Solution description
  - the classes, objects, etc and their relationships
- Consequences
  - trade-offs using the pattern