Hello,
time for a new review. -)
I'm sorry that this one is really too late, but unfortunately I don't have much time now.
Today's topic Data Types The Basics
Probably you'll ask yourself What! Data Types They are not really important, so why does he mention this Why is there a complete review about Data Types
Well, it doesn't seem to be important. But it is an important topic to understand the logic behind programming, especially, as it leads to advanced concepts and topics.
So you'll see some really basic topics combined with advanced programming concepts.
Now let's have a look at the structure of this review

 1. What are Data Types
 2. The Primitives
 3. Objects
 4. Boxing

So let's start with the first topic

#### 1. What are Data Types

Well, often the first address users check to find some answers is [Wikipedia][1], which says the following

 In computer science and computer programming, a data type or simply type is a classification identifying one of various types of data, such as real-valued, integer or Boolean, that determines the possible values for that type; the operations that can be done on values of that type; the meaning of the data; and the way values of that type can be stored.

Long sentence, short meaning To be able to identify a type of data, for example a number, there have to be data types. With data types you can ensure that your number, is a number in your program and therefore you can call some methods on this number, for example you can convert it into a string.
You can't convert a string into a string or an object into a string and you can loop through an object, but it wouldn't make sense to loop through a number and that's why it isn't possible and that's why there are different data types.
= Different data types require different behaviour.
Actually there are only some data types. And one important class of data types are the Primitives.

#### 2. The Primitives
There are lots of things and people being called [Primitive][2], but we'll deal with the data types. In JavaScript there are `5` primitive data types

 - Strings A string is a sequence of characters. In JS you have to use either single quotes `'` or double quotes `` to create a string. Examples Hello! or 'I love JavaScript!'.
 - Numbers A number simply is a number. -D However, there are integers, which are numbers, which don't contain a decimal point, and floats, which contain a decimal point. You create a number in JS by writing the number (without quotes); examples `1.5`, `6`. There is also another number, called Infinity. JS will return `Infinity`, if your number is too big. But usually (when dealing with big, but not huge numbers) JS will use the [scientific notification][3]. However, there is another number, which actually isn't a number `NaN` (Not a Number) is a number, too. ;-)
 - Booleans The boolean data type can contain two values `true` or `false`. Comparisons will evaluate to booleans, so your program will be able to make decisions.
 - undefined Well, if you didn't assign a value to your variable or if it doesn't even exist, you'll see the value `undefined`.
 - `null` `null` simply means nothing. So if there is a variable, whose value has been set to be empty, it will contain the value `null`. The difference between `undefined` and `null` is quite hard to get. Often APIs and DOM methods will return `null`, to show It has been tested, but it doesn't work in your browser.

That was quite a lot of information. -)
Let's continue with objects.

#### 3. Objects
Well, everything but the primitive data types is an object. Functions are objects. Arrays are objects.
That's why talking about data types is important You see the importance of objects.
An object is something, which can hold data and functions. But we've said functions are also objects. How does this work
Well, there is something called the prototype chain. We'll cover this in another review. And the `Object` object is the head of the chain. So all objects, all functions are descended from this object.
And that's why there are only the following data types in JS `Strings`, `numbers`, `booleans`, `undefined`, `null` and `objects`. ;-)

But we've said that only objects can own properties or methods. And I know strings have a `length` property. How does this work
Well, there is something called Boxing.

#### 4. Boxing
I've found a nice explanation [here][4]

 Whenever you access or assign to a property of a number, string or boolean, a temporary object value (of the Number, String or Boolean class, respectively) is created with the same naked value as the primitive value, but that temporary object is only available to that property access, and does not replace the primitive value that your variable references.

To sum it up Your primitive data type stays as it is, but JS creates a temporary variable, which contains the same value while being an object, so you can access some properties.

That's it. -)

Courses
httpwww.codecademy.comdecoursesprimitives-development-course

Ending
I hope you enjoyed this review. -)
But I also hope I didn't make any mistakes, as this topic is quite complicated, as there are lots of details and lots of wrong or imprecise information.
This is a quite long review without bigger examples. I think the difficulty of this topic is one reason, why I didn't write this review before.
The next review dives even deeper and you'll learn about variables and the (weird) `typeof` operator.
However, I would love to read feedback, suggestions and also corrections of wrong information. -)
I hope it helps. -)


  [1] httpen.wikipedia.orgwikiData_type
  [2] httpen.wikipedia.orgwikiPrimitive_%28disambiguation%29
  [3] httpen.wikipedia.orgwikiScientific_notation
  [4] httpprincepthomas.blogspot.de201107auto-boxing-javascript-primitive-types.html