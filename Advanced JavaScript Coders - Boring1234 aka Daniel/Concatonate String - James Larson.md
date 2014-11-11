 - `+` to concatenate strings, 

How could something as simple as the plus `+` symbol be confusing? 

Well, when it has to do double duty in a language like JavaScript!

Let me explain. One of the more powerful capabilities of any programming language is the ability to manipulate strings. What is a string, you ask? Nothing more than a number of characters that is taken as a group!
```
"I am a string."
'I am also a string!'
```
The above are known as *string constants.* Sitting by themselves like that, they aren't very useful, but you can do many things with them, for instance:
```
var s = "Assign this string to variable called s";
console.log("Print this string on the display.");
alert("Show this in an attention grabbing alert box.");
```
Ok, so now we've seen what strings are, and some of the ways they can be used. But another thing you can do is *concatenate them.*

```
"This is a short string. " + " And this is another."
```
After JavaScript gets done with the above, we get,
```
"This is a short string.  And this is another."
```
A longer, single string!

So, why the confusion I spoke of?

Well, it has to do with the two facts: 
   A) JavaScript is a *loosely typed language* 
   B) `+` is also used to do numeric addition. 

Consider the following:
```
var s = "1" + 2 + 3;
```
What would you expect the `s` variable to be?

If you said the number 6, you'd be wrong. This is because JavaScript does *type conversion* before performing the add operation. You think you are adding three integers, but JavaScript is *concatenating three strings!* The actual result is....
```
"123"
```
a string!

Now, it should be pretty obvious in the last example what's going on, but what if you have this bit of code:
```
var a = "1"; // a is a string...
var b = 2; // b is assigned an integer
var c = 3; // c is assigned an integer...
var s = a + b + c;
```
See how you could be confused? If the assignment of the variables a, b, and c occur far upstream of that last assignment which combines all three, you might be scratching your head a little!

But it gets worse...

Consider this:
```
var a = "1"; // a is a string...
var b = 2; // b is assigned an integer
var c = 3; // c is assigned an integer...
var s = b + c + a;
```
What do you think `s` will wind up containing?

Let's think about it: addition is supposed to be commutative, meaning that the order of operations doesn't change the result, right? Well, if we were talking about simple numeric addition, you'd be right! The trouble is, this isn't that! 

JavaScript evaluates the `+` operators in the order that it sees them. So, `b` is 2 - a number - and `c` is 3 - also a number - which yields 5 - yet another number. But then comes `a` - which is a string - and that changes *everything!* The final result is 51 - a string!

The good news is these rules are pretty straightforward, and once you've studied them, they really shouldn't cause any fits.

**Exercises:**

Given your new understanding of concatenation, what will be the result of the following operations:

"1" + (3 + 7)
"10" + 3 + 8 + 9
1 + ("3" + 7)
5 + 6 + ("3" + 7)
1 + 2 + 3 + 4
"Hello! " + "Goodbye!"

Note: Remember that any operation in parenthesis happens *first*.
Use the Codecademy labs to discover the correct answers...

[Return To Master Menu](http://www.codecademy.com/groups/advanced-javascript-coders/discussions/53307af3631fe9e8de00103b#discussion-53307af3631fe9e8de00103b)