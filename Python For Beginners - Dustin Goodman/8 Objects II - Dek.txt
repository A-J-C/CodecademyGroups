Hi, I'm DeK, and this is my first lesson on this group. I'll take on from what Dustin explained to you last week, and try to guide thru the simple but powerful concept of objects.

As you've seen [last week](http://www.codecademy.com/groups/python-fro-beginners/discussions/50f4e37bd6f3f2aaf1000451), classes are the base of object oriented programming (OOP), because they're the way to define your own objects.

Objects are the constructs that allow you to keep the structure and the related behaviour of your application in the same place. By structure, we mean the data your application operates upon. By behaviour, we mean the operations performed on that data. Keeping the operations together with the data upon which they operate, while isolating them both by the rest of your program, is called _encapsulation_ and it's one of the main concepts of OOP.

You already know how to define data and operations for your application in the classic way: 

  - data is represented using variables 
  - operations are represented using functions. 

Now, we're going to see how to define structure and behaviour of our objects. We have already seen how to declare a simple `Circle` class:

    class Circle(object):
        def __init__(self, radius):
            self.radius = radius

and how to create a Circle object, or in tech talk, an instance of Circle:

    circle1 = Circle(5)

So, `Circle` represents all possible circles that your program can deal with, while `circle1` represents an individual circle with radius equal to 5. When `Circle(5)` is invoked, the special "function" `__init__` is executed in order to initialize your object.

An object has instance variables called _fields_ and instance functions called _methods_. The `Circle` class we have defined has a field called `radius`: what does that mean? The field works like a variable, and holds the value of the radius for that particular Circle. What about methods? Let's extend our Circle and give it some behaviour:

    class Circle(object):
        def __init__(self, radius):
            self.radius = radius
            
        def area(self):
            return 3.14 * (self.radius ** 2)
            
        def circumference(self):
            return 6.28 * self.radius
            
    circle1 = Circle(5)

Our circle now has two methods: is it any better? Why yes, it is! Our circle now knows how to evaluate its area and its circumference and return it to us. Notice how we don't need to pass the radius to `area` and `circumference`: these functions already know the value of `radius` because they are encapsulated together with it! In fact, methods are bound to work on the fields of the same object they belong to: so, methods of `circle1` will work on the fields of `circle1`. However, you can pass any additional argument is required, as it is the case with `__init__`.

How to define your own method? Just the way you define a function, with two exceptions:

* you do it inside the `class` declaration;
* the first argument is always the _bound instance_, that is the object upon which the method operates, conventionally called `self`; even though the name `self` is just a convention, it is extremely widespread and you should really avoid using any other name for the bound instance, as well as avoiding using `self` for anything else in your code, in order to keep it understandable to others.

How to call a method? Again, just like a function:

    circle1.area() # This is how you do it!

Once you have your object, you specify the name of the method to invoke and the arguments upon which you want to apply it, again with an exception: the _bound instance_ is placed before the method, separated by a point. This explains why the `self` argument is explicit in the definition of the method, but there's no trace of it when you invoke the method. So, when you write `circle1.area()` you can almost imagine that Python actually reads:

    area(circle1) # THIS WON'T WORK!!!

except that this is not valid Python syntax.

Using fields, that is instance variables, is very simple too. You access them the same way you invoke methods, by prepending them with the object name, separated by a dot:

    circle1.radius = 5 # Assigning a value to a field
    print circle1.radius # Using the value from a field

To define a new field, you just declare it inside one of the instance methods, as if it was a new variable except that, again, it is prepended by the `self` argument. What method should you use to do that? Python gives us the special method `__init__` to initialize the object, and in fact we used it to declare our `radius` field.

Since `__init__` is guaranteed to be executed before any other method, by creating all our fields there we can be sure that they already exist the first time we're going to use them in our code. Hence, in our `area()` method, we can use `self.radius` without worrying about its existence.

That's it for this week. Enjoy!