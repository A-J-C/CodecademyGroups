Week 21 Review: Exceptions
-------------------

A note before starting. Source code is provided as editable fiddles via external links. If you prefer to have all the code on the same page, I've also made a Gist:

https://gist.github.com/nofatclips/5474366

You can also use both... And now, we'ready to discuss how to deal with errors in Python.

Errors happen all the time in writing software. Even when we are sure that our code is bug free, problems may occur due to user misbehavior, OS/Hardware failure or other unpredictable circumstances.

Consider the simple example of a division program:

http://pythonfiddle.com/python-week-review-exceptions/

While the logic seems flawless, there are many things that can go wrong: the user may insert non numeric values, or try to divide a number by zero. This is the kind of error than can and should be anticipated and therefore avoided using `if`s and library functions:

http://pythonfiddle.com/python-week-review-exceptions-avoidance

But let's see a different way to deal with exceptional circumstances, a way that will be useful when detection can't be done in advance: handling exceptions. Which begs the question: what is an exception?

You're used to your function `return`ing a value when everything ends well, right? Well, when things goes awry, functions stop executing and throw `Exception`s at you. When not handled, `Exception`s will make your program crash and exit with an error message: just try dividing by zero in the first program.

In order to handle exceptions, first we wrap the part of our code that can raise problems in a `try` block:

http://pythonfiddle.com/python-week-review-exceptions-passing

The `try` block is followed by an `except` block (in fact one or more `except` blocks. More about this later) which is where we handle the errors. In our example, I just did nothing and `pass`ed: errors are muted. Notice that now, trying to divide by zero doesn't crash the program. This is not good as it seems: we're sweeping the problems under the rug. We don't even know if something went bad!

Let's print a friendly error message like we did in the Error Avoidance version. Problem: how do we tell between "user entered a string" and "divide by zero" errors? That's simple: `except` accepts the error type as a parameter. We can have as many `except` block as type of errors we want to handle.

But first, we need to know what these error types are. Let's run the original program and enter a string. We get:

    ValueError: invalid literal for int() with base 10: 'YOLO!'
    
while if we try to divide by zero, we get:

    ZeroDivisionError: integer division or modulo by zero
    
and now we know we need to handle `ValueError` and `ZeroDivisionError`. The rest is straightforward:

http://pythonfiddle.com/python-week-review-exceptions-handling/

Now you might be wondering: who's throwing these exceptions? Well there's nothing magic about that: in Python you use the `raise` command just to do that. More about that soon. First we need some refactoring!

Let's say that we don't want our function to handle exception: we'll do that in the main program. This is a good practice since when you create a function you don't always know how and when it will be used: therefore, it may or may not be the case that printing an error message on the screen is acceptable. It certainly isn't if we're dealing with a web application. Let's refactor our code:

http://pythonfiddle.com/python-week-review-exceptions-refactoring

Let's also say that we are OK with the `ZeroDivisionError` but we'd like the value error to be more descriptive of what is actually happening. Well, since everything in Python is an object, is no surprise that Exceptions are objects too. We can create an `Exception` with a custom message and use `raise` to send it back to the main program when the user enters a string.

http://pythonfiddle.com/python-week-review-exceptions-raise

But there's a problem: the main program doesn't print the error message we sent. It's clearly a property of the `ValueError` object we created, but how do we access it. In fact: how do we access the object? Well, the `except` keyword has an extended syntax that allows to store the exception in a variable like this:

    except ValueError as the_error:
        pass

Then, we can inspect it as with any other object, or just print it to get the error message:

http://pythonfiddle.com/python-week-review-exceptions-messaging

If you need even more customization, you can extend the `Exception` class and create your own type of exception:

http://pythonfiddle.com/python-week-review-exceptions-custom/

but that's another story.

See you next week.
