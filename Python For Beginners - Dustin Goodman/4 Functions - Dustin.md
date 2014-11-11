This topic is going to open lots of doors for us although most of you probably know the basics of functions. A function is a way to abstract code that you reuse multiply times throughout a script or bigger program. In fact, the last few weeks we've been using special type of function called a method. A method is a function that is for a specific object like a list. We'll get more into these in a few weeks.

The basic form of a function is as follows:

    def function_name(arguments):
        //some code
        return some_value_or_object

Let's break this down a little bit. `def function_name()` is how you define that you're writing a function and the function_name is whatever you want it to be except for reserved system keywords like `this` or `if`. Where I wrote `arguments`, you can put a comma separated list of variable names so you have multiple arguments. If you don't know how many variables you want as an argument, you can write something like `*args` which will take in multiple parameters for the function. We'll talk more about this next week.

So when do we use functions? Whenever we write lots of code and we find we write the same few lines over and over again, we should pull this code out into a function. Let's say we want to compute the area of a circle a few times throughout the script. We could write `radius * radius * math.pi` every time we need the function, or we could write a function like this:

    def circle_area(radius):
        return radius * radius * math.pi

then call it whenever we need it like `circle_area(r)`. Don't you think that's a lot easier than writing it out every time?

That's it for today. Merry Christmas and Happy Holidays to all. Email me if you would like to lead a review or a challenge. :)