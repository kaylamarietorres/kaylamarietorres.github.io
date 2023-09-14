---
layout: essay
type: essay
title: "Inquiring Minds, Smart Outcomes"
# All dates must be YYYY-MM-DD format!
date: 2016-02-06
published: true
labels:
  - Questions
  - Answers
  - Stack Overflow
---

## Are all questions considered valid?

The ability to communicate is one of a software engineer's greatest assets on her coding path to digital enlightenment. Due to how complicated the nature of computer science can get, learning how to ask questions "the smart way" allows the inquirer to gain more productive answers on detailed problems. A 'stupid' question can demonstrate a lack of effort, lack of clarity, redundancy, and trolling characteristics.  

## What constitutes a smart question?
Stack Overflow, an online platform dedicated to programmers seeking answers, serves as a valuable resource for those encountering coding challenges or seeking fresh approaches to problem-solving. Below I have included examples to smart and not so smart questions

Here I found a [smart question.](https://stackoverflow.com/questions/36067767/how-do-i-upload-a-file-with-the-js-fetch-api)
```
Q: How do I upload a file with the JS fetch API?

322

I am still trying to wrap my head around it.

I can have the user select the file (or even multiple) with the file input:

<form>
  <div>
    <label>Select file to upload</label>
    <input type="file">
  </div>
  <button type="submit">Convert</button>
</form>
And I can catch the submit event using <fill in your event handler here>. But once I do, how do I send the file using fetch?

fetch('/files', {
  method: 'post',
  // what goes here? What is the "body" for this? content-type header?
}).then(/* whatever */);
```

This qualified as a good example. They had a clear and descriptive title, provided context, asked a specific question, and expressed effort. Their efforts were rewarded as they recieved a lot of clear and concise help from the Stack Overflow community. 

```
A: This is a basic example with comments. The upload function is what you are looking for:

// Select your input type file and store it in a variable
const input = document.getElementById('fileinput');

// This will upload the file after having read it
const upload = (file) => {
  fetch('http://www.example.net', { // Your POST endpoint
    method: 'POST',
    headers: {
      // Content-Type may need to be completely **omitted**
      // or you may need something
      "Content-Type": "You will perhaps need to define a content-type here"
    },
    body: file // This is your file object
  }).then(
    response => response.json() // if the response is a JSON object
  ).then(
    success => console.log(success) // Handle the success response object
  ).catch(
    error => console.log(error) // Handle the error response object
  );
};

// Event handler executed when a file is selected
const onSelectFile = () => upload(input.files[0]);

// Add a listener on your input
// It will be triggered when a file will be selected
input.addEventListener('change', onSelectFile, false);

```
 
The asker received over 10 possible answers that look clear, conise, and well thoughtout. Due to the success of this question, I believe it to be a good example of a smart question.

## Silly questions

Some questions can express genuine effort, but some show lack of experience and nuance. Here I found an example of a [silly question.](https://stackoverflow.com/questions/1232040/how-do-i-empty-an-array-in-javascript/1232046#1232046)

```
Q: How do I empty an array in JavaScript?

Is there a way to empty an array and if so possibly with .remove()?

For instance,

A = [1,2,3,4];
How can I empty that?
```
A simple google search on arrays would satisfy this request. The asker could have done more research on their potential project along with asking a more detailed question. 
```
A:
A = [];
A.length = 0
A.length = 0
while(A.length > 0) {
    A.pop();
}
```
Despite being a bit of a straightforward question to experienced programmers, to a novice this may seem like a perfectly reasonable question. And while this is true, they still recieved multiple methods of answering this question. 

## Conclusion
As students, when we depend on the generosity and expertise of others to answer our questions, it's important that our inquiries are designed to facilitate efficient and effective help. This not only benefits us but also the individuals assisting us and those who may have similar questions down the road. If you have a question, strive to make it a thoughtful, clear and concise one! While asking questions doesn't guarantee the best answer, phrasing them in a manner that encourages and assists other's response will enhance the likelihood of finding a satisfactory solution and contribute to a positive experience for everyone involved.
