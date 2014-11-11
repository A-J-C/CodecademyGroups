Last week, we talked about function bodies and how to create them. However, we only focused on functions that took a single parameter. This week I would like to discuss creating functions with multiple arguments.

The most basic function I can think of that requires multiple arguments is the area formula for a quadrilateral. It takes in two arguments: length and width. We would write this function as follows:

    def area(length, width):
        return length * width

Fairly straight forward, right? Well, there will be many times you want to pass many arguments to a function. Remember, function parameters can be defined to be any object, i.e. you can pass lists instead of integers or strings or any other object for that matter. A good example is the following function:

    def find_match(arr, n):
       for i in arr:
           if i == n:
               return true
       return false

This is a really bland example lacking lots of examples but it capture the concept that your arguments can be defined to any object. The caveat here is that you must pass your arguments in the same way you defined them in your function. Now, the one of the most powerful tools about Python that doesn't exist in many languages is the splat operator in function definitions. These functions look like this:

    def func(*args):
       #some code here

The splat operator is the `*` before your parameter name. I used the convention that most people use above but you can use whatever variable name you want. This 'splatted' argument is really just an iterable list of the variables you just passed. Here's an example that exists in the Python library:

     def sum(*args):
         n = 0
         for i in args:
             n += i
         return n

You can call this function like `sum(1,2,3,4,5,10,12,13,15)` and it will correctly add these numbers together and return the value. It doesn't seem to be the most useful tool in the world at first glance but has some seriously useful applications.

That's it for this week. Happy New Year and I'll see you all next week.

