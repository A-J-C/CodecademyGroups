Hello,
I know it is **really** late, but now the sixth review is ready.
**Today's topic:** Data Types: Advanced Topics (Part 2)
A long time ago I promised to tell you further things about the `typeof` and the `instanceof` operators and as we've learnt, how to create strings, numbers, booleans and objects and as we've talked about `null` and `undefined` we are ready to learn further things about Data Types. :-)
So let's have a look at the structure of this review:

 1. The `typeof` operator
 2. The `instanceof` operator
 3. The `[[Class]]` property

#### 1. The `typeof` operator

Some of you, who *think they know the `typeof` operator*, might say: "It's a very useful tool, as it tells you the type of a value". And that's true. Let's have a look at the following examples:

    console.log(typeof "Hello"); // Prints "string"
    console.log(typeof 12345);   // Prints "number"
    console.log(typeof NaN);     // Prints "number"
    console.log(typeof true);    // Printe "boolean"

So `typeof` seems to be a really useful operator and it has even more power:

    console.log(typeof function(){}); // Prints "function"
    console.log(typeof []);           // Prints "object"

It tells us that the array is an object, which proves that everything, but a primitive value is an object in JS!
Unfortunately it doesn't tell us that our function is also an object, but this is okay.

    console.log(typeof new Number(12345));
    console.log(typeof new String("Hello"));
    console.log(typeof new Boolean("World!"));
    console.log(typeof null);

Can you guess, what it prints?
Please try it out. :-)
**Maximum surprise:** It prints `"object"` four times. So `typeof new Number(12345) !== typeof 12345`, which is **really** weird.

And that's why the `typeof` operator is dangerous: It works perfectly ... as long as you don't use constructors.
Furthermore the fact that it always prints `"object"` is not always useful: Sometimes we want to know, whether we are dealing with an array or a regular expression. But `typeof` doesn't make a difference between these.
Conclusion: The `typeof` operator is dangerous, as it is *easy it use it, but hard to understand it and even harder to use it correctly*.
*Further information:*
[JavaScript Garden][1] recommends to use the `typeof` operator to test for undefined values and [Crockford][2] has written his own `typeOf()` function.

*So are there better ways to test types correctly? What about the `instanceof` operator?*

#### 2. The `instanceof` operator

Let's have a look at some examples first:

    console.log(new Number(12345) instanceof Number);      // Prints true
    console.log(new Number(12345) instanceof Object);      // Prints true
    console.log(new String("Hello") instanceof String);    // Prints true
    console.log(new Boolean("World!") instanceof Boolean); // Prints true
    console.log(new Boolean(5) instanceof String);         // Prints false

Actually, `instanceof` seems to be a great operator! :-)

    console.log(new RegExp("Code") instanceof RegExp); // Prints true
    console.log(new Date() instanceof Date);           // Prints true
    console.log(new Date() instanceof Object);         // Prints true
    console.log(new Array() instanceof Array);         // Prints true
    console.log(new Array() instanceof Object);        // Prints true

Wow, that's really awesome and helpful! So what does the `instanceof` operator do?

> The instanceof operator tests whether an object has in its prototype chain the prototype property of a constructor.

(Quotation from [MDN][3])

Hm, I think the keyword is **object** and I start to get a bad feeling.
We already talked about *Boxing* in review 4 and *now* we need it to understand the following examples:

    console.log("Test" instanceof String); // Prints false
    console.log(12345 instanceof Number);  // Prints false
    console.log(true instanceof Boolean);  // Prints false

You may assume that we get these results, as we use *literals* instead of constructors. But this can be disproved by the following examples:

    console.log({} instanceof Object); // Prints true
    console.log([] instanceof Object); // Prints true
    console.log([] instanceof Array);  // Prints true

From these we can conclude that `instanceof` has a problem with the *Primitives*: As these aren't objects, `instanceof` returns `false`. And as *objects* and *arrays* are objects, `instanceof` returns `true` in the last examples.

And that's why the [JavaScript Garden][4] recommends the following:

> It is only useful when comparing custom made objects. Used on built-in types, it is nearly as useless as the typeof operator.

So now you've read almost a book and you still don't really know, what to use.
But you know, what you *shouldn't use*. And probably you understand JS as a whole a little better.
Now we should have a look at the best solution.

#### 3. The `[[Class]]` property

Every object has a `[[Class]]` property. If you try to access the value of a string, you get `"[object String]"` and if you try to access the value of a number, you get `"[object Number]"`, as the literals are converted to objects and as objects have this weird, but extremely useful `[[Class]]` property, it works perfectly. :-)
**We found the solution!**
You may read [here][5] for further information about the `[[Class]]` property and other properties. You can access it by passing in something to `Object.prototype.toString.call()`; more information is available [here][6].
First bunch of examples:

    console.log(Object.prototype.toString.call("Hello"));
    // Prints "[object String]"
    console.log(Object.prototype.toString.call(new String ("World!")));
    // Prints "[object String]"
    console.log(Object.prototype.toString.call(12345));
    // Prints "[object Number]"
    console.log(Object.prototype.toString.call(new Number (12345)));
    // Prints "[object Number]"
    console.log(Object.prototype.toString.call(true));
    // Prints "[object Boolean]"
    console.log(Object.prototype.toString.call(new Boolean ("abc")));
    // Prints "[object Boolean]"
    console.log(Object.prototype.toString.call(undefined));
    // Prints "[object Undefined]"
    console.log(Object.prototype.toString.call(null));
    // Prints "[object Null]"

So the useful thing is that we use a method *every object has*, as `Object` is the head of the *prototype chain*.
[JavaScript Garden][7] slices the brackets and the `"object"` and now the output has a better form, so I can show you that this method also gives good results, when dealing with other built-in objects:

    console.log(Object.prototype.toString.call(function(){}).slice(8,-1));
    // Prints "Function"
    console.log(Object.prototype.toString.call([]).slice(8,-1));
    // Prints "Array"
    console.log(Object.prototype.toString.call(/test/).slice(8,-1));
    // Prints "RegExp"
    console.log(Object.prototype.toString.call(new Date()).slice(8,-1));
    // Prints "Date"

**This is awesome!**
Unfortunately it doesn't work [perfectly][8] in IE 7 and IE 8 and unfortunately it doesn't work when using *custom made objects*, but I'm sure you are able to cover this. :-)

**Ending**
I hope you enjoyed this review. :-)
And I also hope you understood *everything*.
I'd like to read your suggestions. Special thanks go to the people, who've answered, commented and helped the last time. :-)
The next review deals with operators. I hope it will be ready before Christmas. :-D
Thanks for reading. `:-)`

  [1]: http://bonsaiden.github.io/JavaScript-Garden/#types.typeof
  [2]: http://javascript.crockford.com/remedial.html
  [3]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/instanceof
  [4]: http://bonsaiden.github.io/JavaScript-Garden/#types.instanceof
  [5]: http://ecma-international.org/ecma-262/5.1/#sec-8.6.2
  [6]: http://ecma-international.org/ecma-262/5.1/#sec-15.2.4.2
  [7]: http://bonsaiden.github.io/JavaScript-Garden/#types.typeof
  [8]: http://stackoverflow.com/questions/14325792/when-does-object-prototype-tostring-callnull-return-object-object