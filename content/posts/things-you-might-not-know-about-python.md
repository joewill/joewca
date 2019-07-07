---
title: "Things You Might Not Know About Python"
date: 2017-09-01
draft: false
---

A few weeks ago I decided to pick up a new programming language. I've always sort of had my eye on [Python](https://www.python.org/). Until recently I hadn't taken the time to try it out. I'm very happy I did. So far it's been a great experience.

I have to admit, I didn't know a lot about Python going in. So I was surprised by what I've learned about the language. I thought I'd share a few of these things. If you've never taken a look at Python yourself, maybe you'll learn something that may resonate with you.

### It's more popular than you think

I had no idea how popular Python is. The first clue was when I went to sign up for my local [Python Meetup Group](https://www.meetup.com/ottawapython/). The next scheduled Meetup was full with 100 people, and a large waiting list.

This just isn't local to Ottawa. According to [Stack Overflow's 2017 Developer Survey](https://insights.stackoverflow.com/survey/2017#technology), Python is the 5th most popular language. Recently overtaking PHP. Other organizations have Python ranked even higher. [Redmonk](http://redmonk.com/sogrady/2017/03/17/language-rankings-1-17/) has Python ranked third.

### Python is used for everything

It's surprising how many things Python can be used for. It's no wonder the language is so popular. It's almost overwhelming. I'm hoping the following examples can show what I mean:

- Web Development? Check. Popular web frameworks Django and Flask run on Python.
- Hardware? Ever heard of [Raspberry Pi](https://www.raspberrypi.org/)? It runs Python out of the box.
- Machine Learning? Check out [Tensor Flow](https://www.tensorflow.org/api_docs/python/).
- Data Science? [Jupyter Playbook](https://jupyter.org/) looks really cool.
- Astronomy?! I recently watched a talk by Jake Vanderplas at PyCon 2017. If you're interested in Space and Python, it's a must watch: [Jake Vanderplas - Keynote - PyCon 2017](https://www.youtube.com/watch?v=ZyjCqQEUa8o)

This isn't everything. Further examples could include things like DevOps and Desktop Applications. I'm sure there are many more. The point is, if you can think something up, chances are you can build it in Python.

### Dynamically Typed

When you declare a variable in Python, you do not specify a type. Such as string, integer or float.

If you've been programming with Javascript, this will seem natural to you. If you're more used to statically-typed languages such as C# or Java than this might take some getting used to.

My opinion on static vs dynamically typed language is mixed. I appreciate the help static typing gives you. Sometimes I prefer the simplicity of grabbing a variable and using it. Not having to think too much about what it is.

I wish I could remember where I read, or heard this. One experienced developer was talking about the increase of bugs in dynamically typed languages. Their response was they like to write lots of unit tests. Which seems very valuable to me.

### White space matters

In Python, the indentation of a block of code matters. When you define a function, all code that belongs to that function must be indented. Same goes for things like if statements.

Take a look at the below code sample. We define a function "indentation_example". Then we indent the code that belongs to the function. Same goes for the if statement a bit further down. Notice the lack of curly braces.

```
def indentation_example():
    result = call_to_other_function()

    if result == 'Cool'
        return True
```

It's taken me a bit to get used to this. The small amount of Python code I've written so far has been readable.

### Colons are my new Semicolons

You may have also noticed in the sample above that there were no semi-colons. Coming from languages such as Javascript or C#/Java this can take some getting used to. If you're one of those Javascript programmers that doesn't use semi-colons, you may be right at home.

You may also have noticed the use of a colon in the example. This is like your starting curly bracket when defining a block of code in another language. Then the block of code is indented, and there isn't a need for a closing character.

The colon is something I've been forgetting to add in. I'll define my function signature, then indent my block of code. Leaving out the colon. It's something I'm getting better at as I write more Python.

### PEP8 Standard

Python comes with it's own style guide. It's called [PEP8](https://www.python.org/dev/peps/pep-0008/) (Python Enhancement Proposal 8). PEP8 defines many rules for how Python code should look and feel.

A few examples:

- [Tabs or Spaces](https://www.python.org/dev/peps/pep-0008/#tabs-or-spaces)
- [Whitespace in Expressions and Statements](https://www.python.org/dev/peps/pep-0008/#whitespace-in-expressions-and-statements)
- [Naming Conventions](https://www.python.org/dev/peps/pep-0008/#naming-conventions)

The documentation is nice for everything PEP8 covers. It's worth it to read through to get a feel for everything it covers.

As someone new to the language this takes a lot of the guess work out for me. I'm not second guessing if my code is ["Pythonic"](https://stackoverflow.com/questions/25011078/what-does-pythonic-mean) or not. If I question myself I can look it up in PEP8.

### Batteries Included

If you do look into Python, you'll likely hear it described as "Batteries Included". This means you can do a lot with the language out of the box. Python comes with a large standard library that's immediately available.

They've designed it this way to allow developers to get their applications up and running. In my short time with the language I'm impressed with how nice it is to have those batteries included.

One good example of this is the [os module](https://docs.python.org/3/library/os.html). This module allows the developer to easily interface with the operating system the program is running on. You can write the same code for Windows, macOS and Linux without having to worry about the details of that operating system.

If you've never tried out Python before I'm hoping something I've written in this post inspires you to give it a try. If you do than [let me know](https://twitter.com/joew_ca) what your initial impressions are.

If you've already been writing Python for a while, than perhaps I'm missing something incredible about the language. In fact I know there's stuff out there that I could add. Let me know what you think everyone should know about Python.

Joe
