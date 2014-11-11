Today we're going to start a multi-week tutorial on objects. This week, we're going to discuss what is an object and how to define one.

To make things complicated, everything in Python is actually an object. That means whenever you create a new variable, you're actually creating a new object. An object is a programming construct that contains information regarding some general use variable that can define any real world object. Objects are defined by classes which can contain data regarding your object and functions that work on your object. These functions have a special name and are called methods. The following is an example of an object, and a method that works on the object:

    str = "This string is an object."
    len(str) #where len is a method of the string class

At this point, you should be saying "Woah there! I know a lot about objects!" which is partially true. You know how to initialize objects and call their respective methods, but you're not always going to use the system default objects when writing programs. Sometimes, you'll need to define your own classes. Think of a class as a blueprint for an object. You put in the blueprint what is needed to make the object and what can be done to it, but you don't actually create it. The basic outline for any class is as follows:

    class NewClass(object):
        #class definition goes here

We'll talk more about this class definition later, but note for now how it looks a lot like a function call. It works very similarly which is really handy since we know this syntax. The last thing we'll do this week is show you how to define your new function. Inside of your class definition, you need a function called `__init__()` (note the use of two underscores on each side of init) which takes at least one argument which is `self`. Again, we'll talk more about the use of self and this definition line in the next couple of weeks. For now, you need to know the following is how you would define a circle object in Python:

    class Circle(object):
        def __init__(self, radius):
            self.radius = radius

To create a new Circle object, you would write the following:

    circle1 = Circle(5)

The above will create a new `Circle` object and give it a radius of value 5. Note, you don't need to pass a parameter for self and you don't need to call `__init__()` when defining the new object. We can access the value of the radius of this circle by typing `circle1.radius`.

That's it for this week. I'll be back next week with more on objects. If you have a request of any topics you would like to see discussed, please [email][1] me your thoughts and suggestions.

  [1]: http://sharocko@gmail.com