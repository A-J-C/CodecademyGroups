Hello,
it's time for the next review. :-)
Last week we've covered the basics of data types, so now we have to dive deeper:
**Today's topic:** Data Types: Advanced Topics (Part 1)
I promise to give you more code examples this time, as this topic isn't as theoretical as the one before. :-)
Last week we've mentioned some special things, for example that `Infinity` and `NaN` are numbers, and this week we'll learn even more interesting things, as the following is the structure of the review:

 1. Variables
 2. Data Type Constructors

#### 1. Variables

This is a topic you all should know. ;-)
You use variables to store some *data*. So if you want to use the string `"Hello!"` many times, you'll want to use variables, so you won't write the string again and again.
Furthermore you often call functions and you might want to store the result in a variable, so you don't need to call the function again and again, so [don't repeat yourself][1]!
We'll also review the data types, when creating our variables:
*(Remember, variable declarations and assignments end with a semicolon `;`.)*

    var myString = "Hello!";
    var myNumber = 12345;
    var myBool = true;
    var myUndefined; // We don't need to assign `undefined` to it, as the value isn't defined ;-)
    var myNull = null;
    var myObject = {};

So now we're able to print these values without repeating (this is also very handy, when using long strings):

    // Bad solution:
    console.log("Hello!");
    console.log("Hello!");
    // Better solution:
    console.log(myString);
    console.log(myString);

That was the *review part* in this review. :-D

#### 2. Data Type Constructors

Some of you might remember the *object* constructor:

    var myObject = new Object();

So you simply use the `new` keyword to create a `new Object`.
However, there are further constructors and we'll have a look at these, which are important when dealing with data types:

    var myString = new String("Hello!");
    var myNumber = new Number(12345);
    var myBool = new Boolean(true);
    console.log(myString);  // Should print "Hello!"

These behave just as other variables behave, too.
However, have we created objects now?
Well, we *have* created some [string objects][2] now.  (Remember *[boxing][3]* when reading the linked part called *Distinction between string primitives and String objects*)
So we are encountering another interesting point here.

And a further thing, which is interesting, is the fact, that we're now able to check the Boolean values of some values.
Sounds confusing, but it is really useful:
When we use `while` loops, we have to add a condition. And often we don't compare whether the `condtion === true`, which allows us to use `0` and `""` as falsy values, too.
And we can check these values using the Boolean constructor:

    console.log(new Boolean("Hello!")); // Prints true
    console.log(new Boolean("")); // Prints false
    console.log(new Boolean(3)); // Prints true
    console.log(new Boolean(0)); // Prints false

So we've learned a further interesting thing about JavaScript. :-)
I'd suggest using the usual way to assign values, but without this way, we wouldn't be able to learn more about conditions *and* the further topics. ;-)
However, we are going to learn a better way to check the value of a condition in a later tutorial. :-)

There are still lots of constructors, which could be mentioned, but these might be mentioned in another review. ;-)

**Note:** I've tried to make the examples using constructors running, but unfortunately it didn't work. However, this doesn't mean the examples are wrong, it just means they aren't supported by the labs. ;-)


**Ending**
As there are no further courses, this is the end of this review.
I've decided to split up this review, as there are still some topics to be covered and the review would simply become too long. ;-)
I hope you enjoyed this review and I'd like to read some suggestions, as there might be some points I forgot to mention. Special thanks go to the people, who've helped the last time. :-)
The next review will deal with the `typeof` operator, the `instanceof` operator and an even better solution. :-)
As usual, I'd love to read some feedback and some suggestions and I hope this review helps. :-)
Thanks for reading! `:-)`


  [1]: http://en.wikipedia.org/wiki/Don%27t_repeat_yourself
  [2]: https://developer.mozilla.org/en-US/docs/JavaScript/Reference/Global_Objects/String#Distinction_between_string_primitives_and_String_objects
  [3]: http://en.wikipedia.org/wiki/Boxing_%28computer_science%29#Boxing