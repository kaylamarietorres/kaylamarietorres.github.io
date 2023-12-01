---
layout: essay
type: essay
title: "Design Patterns -change tite"
# All dates must be YYYY-MM-DD format!
date: 2023-11-26
published: true 
labels:
  - Design Patterns
  - 
---
<img class="rounded-circle" src="C:\Users\kayla\OneDrive\Documents\GitHub\ICS314\kaylamarietorres.github.io\img\designPatterns\designPatternLogo.png" alt="">

## What are design patterns

Design patterns in Computer Science can be thought of as ***proven solutions to common problems*** that programmers face when designing software. 

Imagine you are building a house. When architects design houses, they often follow certain patterns or blueprints that work well for different scenarios. For example, they might use a particular layout for the rooms, standard techniques for plumbing and electrical wiring, or common designs for windows and doors. 

Similarly, in Computer Science, design patterns are like those proven blueprints or templates for solving specific problems in software development. They're not actual lines of code but rather *general solutions that can be applied to different situations.* These patterns help programmers to create more ***efficient, reusable, and maintainable*** code by providing them with tested methods for solving recurring problems.

## How have I used them in my code

#### Singleton
The singleton design pattern can be described as a "global variable". We have a class, and we ensure that only a single instance of that class can exist. It helps centralize the access point to that resource and prevents unnecessary duplication. However, while Singletons can be handy, they should be used judiciously because they can also introduce potential issues, such as making code harder to test or creating dependencies that are hard to trace.

#### MVC 

The Model-View-Controller (MVC) design pattern is a way of organizing and structuring software applications, especially those with a user interface.
Imagine you are building a system like a music player app. In the MVC pattern, the *model* represents the data and the business logic of the application. In the music player app, it would manage the songs, playlists, and how they're organized. The model is responsible for managing the data and responding to requests for information about the data. The *view* represents the user interface (UI) component of the application. In the music player app, the view would be the screens where you see songs, playlists, buttons, etc. The View displays the data from the Model to the user and sends user actions (like clicking buttons) to the Controller. The *controller* acts as an intermediary between the model and the view. It processes user actions from the View, makes requests to the Model for data or updates, and then updates the View with the new data or changes. In the music player app, the Controller would handle actions like clicking on a song to play, creating a new playlist, or shuffling songs. It translates user inputs into actions that affect the Model or the View.
This separation allows for easier development in teams where different people can work on different components without interfering too much with each other's work. Additionally, it makes the code more organized and easier to understand because each part of the application has a specific responsibility.

#### Observer
The observer design pattern represents a way to establish a relationship between objects in software where one object (called the subject or observable) maintains a list of other objects (observers) and notifies them automatically of any state changes, so they can react accordingly. Think of it like subscribing to a newsletter or a magazine. You sign up to receive updates, and whenever there's a new edition, you automatically get notified. 

So, when the state of the subject changes (for instance, the weather changes from sunny to rainy), the subject notifies all its registered observers about the change. Each observer can then react accordingly; for instance, a weather display screen might update to show the new weather conditions. The Observer pattern is useful in scenarios where you have one-to-many dependencies between objects, and you want to decouple the objects involved.

#### Factory

A factory in computer science refers to a design pattern used to create objects without specifying their exact class type explicitly. It's like a factory in the real world that produces various goods without you knowing the intricate details of how each item is made. In software, factories are used to create objects in a flexible and decoupled manner. They allow you to create objects based on certain conditions or parameters without exposing the complexities of their creation process. This helps in writing cleaner, more maintainable code by centralizing object creation logic and promoting code reusability.

#### Publish-subscribe
The publish-subscribe (pub-sub) pattern is a messaging pattern used in software architecture to facilitate communication between different parts of an application or between different software systems. It enables components to communicate with each other without needing to explicitly know each other's identities. The publisher, or producer, is responsible for generating messages or events. The subscriber, or consumer, are interested in receiving specific types of events. They subscribe to certain types of messages without knowing who the publishers are. The message broker, or broker, is an intermediary between publishers and subscribers who receives messages from publishers and delivers them to subscribers based on their interests or subscriptions. 

#### Prototype
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