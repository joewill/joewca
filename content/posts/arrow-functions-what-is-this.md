---
title: "Arrow Functions: What is this?"
date: 2017-03-25
draft: false
---

Arrow functions are a newer feature in Javascipt. They are very handy, often creating cleaner, more concise code. They do come with some gotchas. One of these gotchas being how the `this` keyword is handled.

Before we get to `this`. Lets take a quick look at what an arrow function is. Traditionally in Javascript you would define a function like so:

```
function oldSchool(){
  return "The way we've always done it";
}
```
...and the arrow function equivalent
```
const newSchool = () => { "One liner!" };
```
Notice the `=>`. This is called a "fat arrow". If you see it in Javascript code, you're looking at an arrow function. It looks a lot like the greater than or equal to [comparison operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Comparison_Operators).

The above example is setting an arrow function to a variable. But in most cases I've seen, they are used as anonymous functions. Like so:

```
const louder = thingsSaid.map((quiet) => {
    return `${quiet}!!!`;
});
```
The above example is for the hard of hearing (like myself). It takes an array of strings (`thingsSaid`) and maps each string in the array to itself with exclamation marks. Producing a new array of strings called `louder`.

We can even turn this arrow function into a one liner:

```
const louder = thingsSaid.map(quiet => `${quiet}!!!`);
```
Notice how I was able to remove the argument parenthesis, curly brackets, and the `return` keyword.

Here's one more example:
```
const ofAge = ages.filter(age => age >= 19);
```
Here we are checking to see if someone's permitted to buy booze in Ontario. We have a combination of an arrow function (`=>`) and a greater than or equal to operator. It looks funky, but totally works. Might not be the most readable example though. Parsing out if you're looking at a fat arrow, or a [comparison operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Comparison_Operators) could get tricky.

Ok, so now we know what an arrow function is. What about `this`? The thing to watch out for is **arrow functions do not re-bind `this`**.

The best example I have seen that demonstrates this is from [Wes Bos'](http://wesbos.com/) excellent [ES6 for Everyone](https://es6.io/) course.

```
const button = document.querySelector('.button');

button.addEventListener('click', () => {
    console.log(this); //this === Window
});

button.addEventListener('click', function(){
    console.log(this); //this === button element
});
```
We first select a button element. Then we attempt to add a click handler to do something when the button is clicked. We want to use a function as the `listener`. When we use an arrow function, the `this` keyword is not bound to the button. When we use a traditional function, it is.

I've seem many examples of arrow functions lately, but I wasn't aware of this. It's one of those things to keep in mind when using these slick new features. If in doubt, the easiest way to determine what `this` represents is logging it out to the console:

```
console.log(this);
```
Another great resource, including more examples, is MDN's page on [Arrow Functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Arrow_functions).

Joe

