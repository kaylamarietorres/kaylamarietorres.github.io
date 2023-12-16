---
layout: essay
type: essay
title: "Design Patterns in Software"
# All dates must be YYYY-MM-DD format!
date: 2023-11-26
published: true 
labels:
  - Design Patterns
  - Singleton
  - MVC
  - Observer
  - Factory
  - Pub-Sub
  - Prototype
  - Front Controller
---
<img class="center" src="..\img\designPatterns\designPatternLogo.png" alt="">

***"Patterns help newbies acquire the hard-won experience of ninjas."*** 

## What are design patterns

Design patterns in computer science are ***proven solutions to common problems*** that programmers face when designing software. 

Imagine you are building a house. When architects design houses, they often follow certain patterns or blueprints that work well for different scenarios. For example, they might use a particular layout for the rooms, standard techniques for plumbing and electrical wiring, or common designs for windows and doors. 

Similarly, in Computer Science, design patterns are like those proven blueprints or templates for solving specific problems in software development. They're not actual lines of code but rather *general solutions that can be applied to different situations.* These patterns help programmers to create more ***efficient, reusable, and maintainable*** code by providing them with tested methods for solving recurring problems.

**[A design pattern] "describes a problem that occurs over and over again in our environment, and then describes the core of the solution to the problem, in such a way that you can use this solution a million times over, without ever doing it the same way twice" -Christopher Alexander, 1977**

#### Singleton
The singleton design pattern can be described as a "global variable". We have a class, and we ensure that only a single instance of that class can exist. It helps centralize the access point to that resource and prevents unnecessary duplication. However, while Singletons can be handy, they should be used carefully because they can also introduce potential issues, such as making code harder to test or creating dependencies that are hard to trace.

#### MVC 

The Model-View-Controller (MVC) design pattern is a way of organizing and structuring software applications, especially those with a user interface.
Imagine you are building a system like a music player app. In the MVC pattern, the *model* represents the data and the business logic of the application. In the music player app, it would manage the songs, playlists, and how they're organized. The model is responsible for managing the data and responding to requests for information about the data. The *view* represents the user interface (UI) component of the application. In the music player app, the view would be the screens where you see songs, playlists, buttons, etc. The View displays the data from the Model to the user and sends user actions (like clicking buttons) to the Controller. The *controller* acts as an intermediary between the model and the view. It processes user actions from the View, makes requests to the Model for data or updates, and then updates the View with the new data or changes. In the music player app, the Controller would handle actions like clicking on a song to play, creating a new playlist, or shuffling songs. It translates user inputs into actions that affect the Model or the View.
This separation allows for easier development in teams where different people can work on different components without interfering too much with each other's work. Additionally, it makes the code more organized and easier to understand because each part of the application has a specific responsibility.

#### Observer
The observer design pattern represents a way to establish a relationship between objects in software where one object (called the subject or observable) maintains a list of other objects (observers) and notifies them automatically of any state changes, so they can react accordingly. Think of it like subscribing to a newsletter or a magazine. You sign up to receive updates, and whenever there's a new edition, you automatically get notified. 

So, when the state of the subject changes (for instance, the weather changes from sunny to rainy), the subject notifies all its registered observers about the change. Each observer can then react accordingly; for instance, a weather display screen might update to show the new weather conditions. The Observer pattern is useful in scenarios where you have one-to-many dependencies between objects, and you want to decouple the objects involved.

#### Factory

A factory in computer science refers to a design pattern used to create objects without specifying their exact class type explicitly. It's like a factory in the real world that produces various goods without you knowing the intricate details of how each item is made. In software, factories are used to create objects in a flexible and decoupled manner. They allow you to create objects based on certain conditions or parameters without exposing the complexities of their creation process. This helps in writing cleaner, more maintainable code by centralizing object creation logic and promoting code re-usability.

#### Publish-subscribe
The publish-subscribe (pub-sub) pattern is a messaging pattern used in software architecture to facilitate communication between different parts of an application or between different software systems. It enables components to communicate with each other without needing to explicitly know each other's identities. The publisher, or producer, is responsible for generating messages or events. The subscriber, or consumer, are interested in receiving specific types of events. They subscribe to certain types of messages without knowing who the publishers are. The message broker, or broker, is an intermediary between publishers and subscribers who receive messages from publishers and delivers them to subscribers based on their interests or subscriptions. 

#### Prototype

The Prototype design pattern is a creation pattern used in software development to create new objects by cloning existing ones, known as prototypes, instead of creating them from scratch. Imagine you have a cookie cutter (the prototype) that shapes cookies in a specific way. Instead of making each cookie individually by hand, you use the cookie cutter to produce multiple cookies that all look the same. The prototype pattern allows you to *clone* existing objects instead of creating new instances of them from scratch. This can be useful when creating new objects are expensive and time-consuming, objects may have complex initialization process, or you need multiple variations of similar objects. 

#### Front Controller 
A Front Controller is a centralized entry point that manages and handles requests coming into a web application. It serves as a single point of contact for handling all incoming requests, routing them to the appropriate handlers or controllers based on the request information. Imagine a large building with multiple entry points, but instead of having several security guards at each entrance, there's one main reception area where all visitors first check-in. The front controller handles the requests such as HTTP requests in web applications. It is responsible for processing these requests, performing any necessary initial processing, authentication, or logging, and then directing the requests to the appropriate components or controllers. Once the Front Controller receives a request, it determines which specific controller or handler should deal with that request based on the request type, route, or other parameters. These controllers then handle the specific tasks associated with the request, such as retrieving data, processing business logic, or rendering the appropriate view.

## How have I used design patterns in my code

I have used  design patterns when working with the Bowfolios module in my software engineering class. Bowfolios is a card component based web app for athletes at UH Manoa created by the ICS department, and studied by ICS students. 

#### Prototype
We have a set of classes in the api directory that are used to encapsulate underlying mongo collections. In this screenshot we can see that the class ProfileCollection has a constructor that creates the profile collection. It includes basic information like username, first and last name. It is considered a *"prototype"* because it's same structure can be used in other card component offerings in other software structures. 
```javascript
constructor() {
    super('Profile', new SimpleSchema({
      username: { type: String },
      // Remainder are optional
      firstName: { type: String, optional: true },
      lastName: { type: String, optional: true },
      bio: { type: String, optional: true },
      interests: { type: Array, optional: true },
      'interests.$': { type: String },
      title: { type: String, optional: true },
      picture: { type: SimpleSchema.RegEx.Url, optional: true },
      github: { type: SimpleSchema.RegEx.Url, optional: true },
      facebook: { type: SimpleSchema.RegEx.Url, optional: true },
      instagram: { type: SimpleSchema.RegEx.Url, optional: true },
    }, { tracker: Tracker }));
  }

```

#### Pub-Sub
Another example within Bowfolios is the Publish method. Publish will create a meteor publication so that when you subscribe to that publication you will get a cursor to the contents to the entire collection, it is a very simple way to think about observer design patterns. If meteor is the server means that only if meteor is on the server side will this method be called. This method will be invoked on startup in the publications. 
```javascript
publish() {
    if (Meteor.isServer) {
        Meteor.publish(this._collectionName, () => this._collection.find());
    }
}
```

#### MVC
In the case of Bowfolios, the Model is MongoDB, the View is Blaze, and the Controller is FlowRouter. MongoDB sends change notifications information to React and receives state query changes from Blaze. Blaze sends user gestures to FlowRouter, and receives view selection from FlowRouter. And FlowRouter sends state change information to MongoDB. The base collection class implements the mongo collections which serve as the model in MVC and are used as an abstract parent collection for the interest and profile collections instances. The view in Bowfolios is the use of Blaze templating language. It loops through and creates directory profile objects. The controller is FlowRouter. Defined in import/router/startup/client/router.js calls FlowRouter to create a landing, directory, and user routes. 
```javascript
import { FlowRouter } from 'meteor/kadira:flow-router';
import { BlazeLayout } from 'meteor/kadira:blaze-layout';
import { $ } from 'meteor/jquery';


/*                        LANDING ROUTE                       */

export const landingPageRouteName = 'Landing_Page';
FlowRouter.route('/', {
  name: landingPageRouteName,
  action() {
    BlazeLayout.render('Landing_Layout', { main: landingPageRouteName });
  },
});

/*                        DIRECTORY ROUTE                       */

function addDirectoryBodyClass() {
  $('body').addClass('directory-page-body');
}

function removeDirectoryBodyClass() {
  $('body').removeClass('directory-page-body');
}

export const directoryPageRouteName = 'Directory_Page';
FlowRouter.route('/directory', {
  name: directoryPageRouteName,
  action() {
    BlazeLayout.render('Directory_Layout', { main: directoryPageRouteName });
  },
  triggersEnter: [addDirectoryBodyClass],
  triggersExit: [removeDirectoryBodyClass],
});


/*                        USER ROUTES                      */


function addUserBodyClass() {
  $('body').addClass('user-layout-body');
}

function removeUserBodyClass() {
  $('body').removeClass('user-layout-body');
}

const userRoutes = FlowRouter.group({
  prefix: '/:username',
  name: 'userRoutes',
  triggersEnter: [addUserBodyClass],
  triggersExit: [removeUserBodyClass],
});

export const profilePageRouteName = 'Profile_Page';
userRoutes.route('/profile', {
  name: profilePageRouteName,
  action() {
    BlazeLayout.render('User_Layout', { main: profilePageRouteName });
  },
});

export const filterPageRouteName = 'Filter_Page';
userRoutes.route('/filter', {
  name: filterPageRouteName,
  action() {
    BlazeLayout.render('User_Layout', { main: filterPageRouteName });
  },
});

/*                        MISC ROUTES                       */
FlowRouter.notFound = {
  action() {
    BlazeLayout.render('Page_Not_Found');
  },
};
```