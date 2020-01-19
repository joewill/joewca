---
title: "Higher Order Functions"
date: 2020-01-19
draft: false
---

One of the really cool features of JavaScript is that you can pass functions around your code. One of the ways you can pass around a function is to set it as the argument of another function. A function that takes another function as one of its arguments is called a _Higher Order Function_.

A function that returns another function is also called a Higher Order Function. But today we’ll focus on passing functions as arguments.

Let’s start with an example. Say we wanted to write a JavaScript function that takes in an array of words. Then the function will log each word in the array, but with a question mark appended to the end. It might look something like this:

```
function addQuestionMarkToWords(wordsArray) {
  for (let i = 0; I < wordsArray.length; I++) {
    console.log(wordsArray[I] + “?”);
  }
}

let words = [“dog”, “car”, “dracula”];
addQuestionMarkToWords(words);
```

Let’s walk through what is happening here. First we declare our function `addQuestionMarkToWords`. This function accepts an array of strings as its first and only argument. Then the function will iterate through the items in the array. For each iteration we add a question mark to the string, then log the string to the console.

Our console output then looks something like this:

```
dog?
car?
dracula?
```

This is great, we accomplished what we set out to do!

Wait, what if we wanted to add an exclamation mark to the end of the string, instead of a question mark? Easy right, that would look something like this:

```
function addExclamationMarkToWords(wordsArray) {
  for (let i = 0; I < wordsArray.length; I++) {
    console.log(wordsArray[I] + “!”);
  }
}
```

Done! Blog post over.

Not quite. What if we wanted to do yet another modification to the string? Say add Ellipses this time?

```
function addEllipsesToWords(wordsArray) {
  for (let i = 0; I < wordsArray.length; I++) {
    console.log(wordsArray[I] + “...”);
  }
}
```

And then perhaps we could write another function that automatically capitalizes the first letter in a word. The possibilities are endless. Our code is starting to look a bit endless as well…

We’re seeing quite a bit of repetition. Which is fine, but that’s a lot of code to maintain. This goes against the “[Don’t Repeat Yourself]([Don’t repeat yourself - Wikipedia](https://en.wikipedia.org/wiki/Don't_repeat_yourself)” rule. We can fix this using a Higher Order Function.

Remember above, we defined a Higher Order Function as a function that takes another function as a parameter. We can define functionality in one function, and pass that function to be used in our calling function. This is a powerful feature that makes writing JavaScript fun.

Our new Higher Order function looks like this:

```
function modifyStringInArray(wordsArray, modification) {
  for (let I = 0; I < wordsArray.length; I++) {
    console.log(modification(wordsArray[I]));
  }
}
```

The key thing to pick up on is the second parameter _modification_. This is the function we are passing into our Higher Order Function. This is referred to as the _Callback_ function. The first function “calls back” to the function passed in.

We can call the callback function, `modification`, using brackets. We iterate through the array of words. For each word we run the `modification` callback function. It’s this functions responsibility to do something to our word. Then return that to Higher Order Function :`modifyStringInArray()`.

Now we just need to write our callback function. This is where we define what we want to happen to each word. A callback function that adds a question mark could look like:

```
function addQuestionMark(word) {
  return word + “?”;
}
```

Then we can put it all together:

```
function modifyStringInArray(wordsArray, modification) {
  for (let I = 0; I < wordsArray.length; I++) {
    console.log(modification(wordsArray[I]));
  }
}

function addQuestionMark(word) {
  return word + “?”;
}

modifyStringInArray(words, addQuestionMark);
```

The output of running this is:

```
dog?
car?
dracula?
```

Exactly the same thing as before.

So now you might be thinking "Hey! So we just broke up our original function and made two that do the same darn thing!”

You’d be right! The beauty comes when we want to start adding more functionality. We can define new callback functions that do different things:

```
function modifyStringInArray(wordsArray, modification) {
  for (let I = 0; I < wordsArray.length; I++) {
    console.log(modification(wordsArray[I]));
  }
}

function addQuestionMark(word) {
  return word + “?”;
}

function addExclamation(word) {
  return word + “!”;
}

function addEllipses(word) {
  return word + “…”;
}
```

Instead of having three functions that are almost exactly the same, we broke out the interesting parts. Our Higher Order Function’s `modifyStringInArray` responsibility is to iterate through the array and call on the callback function. Then log our result out to the console. Our callback function’s responsibility is to modify and return the string.

Lets call our Higher Order Function with our new callbacks:

```
modifyStringInArray(words, addQuestionMark);

//dog?
//car?
//dracula?

modifyStringInArray(words, addExclamation);

dog!
car!
dracula!

modifyStringInArray(words, addEllipses);

dog...
car...
dracula...
```

So much nicer, I hope you agree.

In JavaScript, functions are first-class. They can be passed too, and executed in other functions. They can be returned by functions.

A Higher Order Function is a function that will take another function as an argument, or return another function. This allows us to change the operation of a function. This allows us to do some really fun things.
