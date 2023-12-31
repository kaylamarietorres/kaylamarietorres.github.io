---
layout: essay
type: essay
title: "ESLint and The Journey to Quality Code"
# All dates must be YYYY-MM-DD format!
date: 2023-09-20
published: true
labels:
  - Coding Standards
  - ESLint
  - IntelliJ
  - JavaScript
---

<img width="400px" src="../img/standards.jpeg">

*Standards are established criteria or guidelines that provide consistency, reliability, and consistency across various fields, facilitating uniformity and quality assurance.*

I was pondering on a question earlier this week -- _why do we need coding standards_? Why are we going through all of this trouble to configure ESLint for it to make my life harder? These questions came after my last couple of Software Engineering assignments. 

When I asked a friend, she said that expecting coding to be easy is only fooling yourself, and she said wouldn't I agree that ESLint is taking some of the trouble away from debugging your own code? I agreed, but I thought to myself there has to be a bigger reason why we are using ESLint... 

## The Finer Details

The more I research coding standards, I learn that they have been a topic of debate in the world of software development. Some view them as trivial; who needs to worry about intention and curly brace placement. I, however, enjoy the finer details of coding standards and how they are significant beyond their visual aspects. I believe that creating standards that we can all adhere by as programmers can make life easier for all of us when it comes to collaboration, and working with other's code. When we can read each-other's code easier, we can also learn the language better as a result. 

### Consistency and Readability
Code consistency is a major component of software development. It facilitates adherence to a set of predefined coding standards. Paying attention to the finer details has a profound impact on clarity and maintainability of code. _ESLint is a tool that scans code to bring to your attention deviations from it's established rules._ Using ESLint's uniform code formatting, naming conventions, and bracing styles has helped me learn JavaScript that much more, rather than writing code that doesn't work, and not being sure why. 

### Reducing Bugs and Errors 
By providing a predictable structure, it reduces the load placed on the programmer to write code from a new coding language. It also helps programmers use best practices such as using '===' instead of '==' to check value and data type. For example:
```cpp
5 === 5 // true (both have the same value and type)
"5" === 5 // false (different types)
5 == "5" // true (type coercion)
```
Furthermore, ESLint also helps with syntax errors, like missing a closing parenthesis:
```cpp
// Without ESLint
function sum(a, b {
    return a + b;
}
// With ESLint
// ESLint would catch the missing closing parenthesis
function sum(a, b) {
    return a + b;
}
```
This might seem minute, but for programmers with 1000s of lines of code, this would save a lot of time digging through lines of code to figure out where the error is. However, if that was your code, ESLint would also throw errors for not using either of those functions. (Wow, look at me knowing what ESLint would say after using it for one week... )

## Community

ESLint has an effect on the coding community as a whole by promoting coding standards, best practices, and code quality. By enforcing consistency, it can help programmers work in teams and collaborate more efficiently using each-other's code. And by providing a framework for coding standards, it contributes to the _growth of the coding community as a whole_. 

### Facilitating Learning
Through my week of using ESLint, it has become a tool that I genuinely enjoy using. Keeping stricter coding standards makes me a better programmer and helps me learn JavaScript quicker. Because having a debugging tool that I can click and see what is wrong with my code and why, helps me not to make the same mistake in the future. And, adhering to higher coding standards prepares us programmers for a professional coding environment in the future where many developers must adhere to. These coding standards such as consistency, readability, and reduction of errors are important to me and are the main reasons why I will continue to use ESLint in the future. 
