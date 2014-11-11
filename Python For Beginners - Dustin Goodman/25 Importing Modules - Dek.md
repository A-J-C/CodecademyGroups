Week 25 Review: Importing Modules
============

Hi!
Today we're going to talk about modules. A [module](http://docs.python.org/2/tutorial/modules.html), in its essence, is no more than a script, a file containing Python code. When you're working on a big project, you might want to split your code in smaller modules to keep it manageable; additionally, using modules makes possible to reuse the same code in several projects.

The most prominent case of reuse is obviously the [Python Standard Library](http://docs.python.org/2/library/). Python comes with a set of standard modules that add a lot of useful features to those built into the language. You only need to import them into your own program and use them. How?

Importing and Using a Module
------------------

In Python, you do that with the `import` keyword, followed by the name of the module:

    import someLibrary
    
From now on, `someLibrary` works as a namespace to access the functions offered the the module. That is: in order to call some function defined in `someLibrary`, you're going to use:
    
    someLibrary.someFunction()
    
Coding the function to evaluate the factorial is a good exercise. But using the library function which is included in the [`math` module](http://docs.python.org/2/library/math.html) is certainly faster:

    import math
    print math.factorial(10)

Importing Single Attributes from a Module
-----------------------------------------

Using the namespace to access the functions from a module reminds us where that function comes from, especially when reading code written by other people or by ourselves a long time ago. But sometimes it's overkill: do you really need to be reminded that `factorial` is in the `math` module? For that, Python provides a more concise syntax, using the `from` keyword:

    from math import pi
    radius = 4
    print 2 * pi * radius

Notice that now the module is imported with `from`, while `import` specifies which attributes (in this case a constant, `pi`) you want to extract from `math` and bring into your code.

This is consistent with the fact that **you're not importing the math module**! If you try to call `math.factorial(10)` in the second program you get an error ("math is not defined") because we imported just `pi`, not the whole module.

However, we can specify multiple attributes in our `from ... import` directive:

    from math import pi, factorial
    radius = 4
    print 2 * pi * radius
    print factorial(10)

or even importing all the attributes at once using:

    from math import *
    radius = 4
    print 2 * pi * radius
    print factorial(10)

The Importance of Being Namespaced
----------------------------------

Notice that in the last version of the code there's really no way to infer where `pi` and `factorial` come from by just reading the code. You just happen to know it or you don't (or you have good IDE...)

Therefore, the `from` keyword (and the wildcard version especially) should be reserved for standard libraries or when playing in the Python shell, since the namespacing makes the code clearer.

It's also the best choice when you're importing two attributes with the same name, as rare as this situation might be.

References and Additional Links
----------------

* The code in this review: [Gist](https://gist.github.com/nofatclips/5653733) - [Fiddle](http://pythonfiddle.com/review-week-modules/)
* [Python Koans](https://github.com/gregmalcolm/python_koans)
* [Modules](http://docs.python.org/2/tutorial/modules.html) in the *Python Tutorial*