Hello. This week we’re not going to review any specific topic. We’re going to talk about programs, and specifically two of their main ingredients: **algorithms** and **data structures**. Obviously, I'm just going to scratch the surface: a good coverage would require months and thousands of pages.

Also, the post will focus on two specific data structures (lists and sets) which are built in Python, rather than try a comprehensive discussion of the topic, because this is supposed to be a review after all.

A lot of effort is often put by programmers into devising ways to improve their algorithm, usually to make it run faster. But sometimes, too much effort should ring a bell: it could be the sign that we’re neglecting our data structure.

Data always come first: you can’t write an algorithm without some data for it to operate upon. This may lead to rush the definition of the data structure (do I need to store 100 number? Well, I’m just going to use a list...) in order to start writing some "real code" as soon as possible.

The problem we’ll use as an example is based on [Project Euler](http://projecteuler.net/) Problem #23. I’ve introduced randomness so that we’ll have to rely on our knowledge of programming techniques, rather than maths, to solve it. (And I kinda rushed the code, so there may be bugs in the implementations.)

Here’s the problem:

> Given an ordered sequence of 5000 integers, find all the numbers between 1 and 50000 that cannot be expressed as the sum of two of those integers and return their sum.

Simple, right? Here’s a very simple implementation.

https://gist.github.com/nofatclips/5117027

Very bad also: it takes almost 3 minutes just to go from 1 to 5000!!! Let’s examine the code. Ignore the `timeit` decorator, we use it as a stopwatch; the `generate...` method creates a list of random numbers, our addends; `findSum()` iterates over the values in the given range `[1...50000]` and sums those that are not the result of x+y, with x and y being any number in the list of addends.

The actual logic to check if a value is the sum of “addends” is in the `checkSum()` method: for every value, it checks if each couple of addends sums up to our value. This means that for 5000 addends, for each value we make `5000*5000` = 25 millions checks per value; we have 50000 values, so we make `25*50 billions` of checks. We can certainly improve on that.

A simple modification to the algorithm can make it faster, especially for big ranges of values.

https://gist.github.com/nofatclips/5117172

It still requires a ludicrous amount of time (55 seconds) just to get up to 5000. What did we change? In `checkSum()`, we just check for a single value; since we already know the sum, given the first addend we just need to search for `addend2` = `sum-addend1` in the addends: if found, then we discard the value, otherwise, we return True, and the value is added to the total. This way, we only perform 5000 checks per value. But now a check is something different (and slower) than before.

In the first algorithm, we were just checking for equality

    number == addend1+addend2

while now we are checking for inclusion

    (number-addend1) in addends

To check if `number-addend1` is not included in `addends`, Python will need to visit the whole list: so internally, each check can actually be composed of up to 5000 checks. We only gain something when the value is found before the list reaches its end.

Still, the idea sounded right. If only there was a better way to search through a list. But wait... Why a list? Well, because we needed to store numbers and we just decided to use a list without thinking too much about it. A list gives direct access to each value stored in it (using the square bracket notation) and in a defined order. Our algorithm doesn’t need any of this. It only needs to know if a value is or is not in our set of addends. What did I just say? Set. That’s it.

Using a set instead of a list, will allow us to bargain direct ordered access for speed:

https://gist.github.com/nofatclips/5117356

The code is exactly the same, because sets and lists have a similar set of methods and properties (more formally, they implement the same interface), except that `nums` (the addend collection) is now converted to a set before being sent to `findSum`. The result is astonishing: 0.2 seconds.

To explain how sets achieve their degree of performance is beyond the purpose of this post (you can google for **Hash Table**) but the main concept is that rather than using a single huge list, a set is internally composed by many smaller lists, and Python always knows in which list to search for a value, in the same way you know that if you’re looking for “Set” in the encyclopedia, you only need to search the “S” volume rather than the whole thing.

The catch here is that the objects in a set must be immutable. Imagine what would happen if one weird day, the word “set” started with the letter “C”. You would look through all the “S” volume of the encyclopedia and since there would be no trace of “set” (now it’s placed in the “C” volume) you conclude that the word "set" does not exist anymore!

That's why elements stored in a set cannot change their state. Therefore, the set is not the magic tool to solve all our problems: it’s OK in this case, but sometimes we’ll need to deal with mutable objects or with their mutual order. We could think of many ways to improve the list version leveraging the fact that the list is ordered or inverting the logic. But I'll leave it up to you.

The point, here, was not to show how to work on random numbers. The point to be taken is that you should pick the right data structure *with* the right algorithm: one won’t work properly without the other. When there’s none available, use the built in types as your bricks and make it yourself. But that's another story...

**P.S.** To copy the code from Github use the *Download Gist* button on the left or click the *View Raw* button (the `<>` one) on the right. Otherwise you'll lose indentation.