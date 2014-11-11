This week we're going to look at a question brought about by [hashmi786](http://www.codecademy.com/hashmi786). He asked what the significance of the parameters were in the following function header:  `def foo(*args, **kwargs,***kkwargs...)`. After some careful research and programming, I've found a need to update his  question a little bit. The only valid form of the function he proposed is `def foo(*args, **kwargs)`. A parameter with more than two `*` is invalid and will throw a syntax error.  Therefore, today's discussion is the `**kwargs` parameter.

As you already know, you can call functions like:

    def foo(x):
        return x*123;

    def bar(*args):
        sum = 0
        for i in args:
            sum += i
        return sum

where `x` is a normal function parameter and `*args` is a splat argument (i.e. a function can take a variable number of parameters and puts them together in an array). If these don't seem familiar, please see the reviews for week 4 and 5.

The `**kwargs` parameter is similar to the `*args` parameter in that it creates a data structure. In this case, it will create a dictionary (will cover next week) instead of an array. So, how do we use this new argument? When you define a function like `def foobar(**kwargs)`, you have to pass your arguments like `foobar(a=15, b=17, c=5)`. "But Dustin, why are you assigning variables in a function header?" I'm not actually defining variables. What I'm doing is defining the key-value pair for each member of the dictionary that I'm passing in. Again, we'll discuss the details of dictionaries next week but it is important to understand that you have to pass in a variable with both the key AND the value otherwise you'll have an error. 

One more thing, you can combine all three types of function parameters, i.e. `def amazing(param, *args, **kwargs)`. The only note to make is to make sure you define them in the correct order. So the mandatory argument must be first, all non-dictionary arguments must come next and the dictionary elements come last. Your mandatory arguments must come first but the special parameter operators can come in either order. Also note that you cannot use the same operator twice, i.e. `def bad(*args, *args1)` is invalid and will throw an error.

That's it for this week. If you have any questions, let me know.