---
title: "Filling in the Gaps: C# Access Modifier"
date: 2017-01-21
draft: false
---

Every year I get an education allowance through work. Every year I feel like I don't take full advantage of it. This year I choose to spend a portion of my allowance on a [PluralSight](https://www.pluralsight.com/) subscription.

I've been a professional developer now for 11 years. That's a long time. You might think I know my tools inside and out by now. I would say I'm very productive, but I don't know everything.

Getting back to PluralSight. They have a feature called "Paths". PluralSight offers video course training on many topics. Paths is a feature that guides you through a Topic from A to B. They direct the learner through a topic from Beginner to Advanced. Stringing together video courses that teach the learner along the way.

Before you get started on a Path you do a quick 5 minute test. I took two. One for C#, the other for Javascript. These are the programming languages I'm most interested in mastering.

While I did very well in the Javascript test, I did not do so well in the C# test. This was surprising to me as I feel my C# skills are higher than my Javascript skills. Needless to say, I was a bit humbled.

I took this as a sign to buckle down and fill in the C# gaps. By "gaps" I mean knowledge gaps. The things I thought I understood but didn't. I started down the C# "Path".

I'll give an example of one such "gap". That is the `Access Modifier`. Now I've been using these for years, but had no idea what they were called. It's not terminology we use around the office.

So what is an Access Modifier? Consider the below C# code:

```
public string Greeting(){
  return "Hi!";
}

private string Greeting(){
  return "No soup for you!";
}
```

Notice the difference between those two functions? The private/public keywords. Those are Access Modifiers. If you had asked me a couple of days ago I don't know if I could have told you what the actual name was. I would have likely said they're part of the function signature.

So what do they do? `Private` limits the function to the enclosing class. You cannot call this function from code outside the class the function is defined in. `Public` allows the function to be called from code outside the class.

These aren't the only two Access Modifiers. There are others such as `protected` and `internal`. If you're curious what these do I would head to the [official documentation](https://msdn.microsoft.com/en-us/library/wxh6fsc7.aspx).

I recognize this isn't a great example of something that's going to make me more productive using C#. But it's an example of one of those things I know now, that I didn't before. That's called learning. Something I'm excited to do more of.

Joe
