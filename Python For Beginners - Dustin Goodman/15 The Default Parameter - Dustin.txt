Over the last couple weeks, I've seen several questions about special features   in regards to function calls. This week I thought it would be good to start accumulating all these discussed features into review threads and to expand on the material discussed.

If you have a function with lots of input parameters, but you're finding that you're defining one input the same way every time, then you might want to consider using a default value for this parameter. This allows you to ignore the value during the call to the function. It is important to note that you have to be careful when writing a function with default parameters. 

Functions have two types of parameters: mandatory parameters and optional parameters. If you define a parameter to have a default value then it becomes optional. If the parameter doesn't have a default value, then it is mandatory. Let's make this clear through an example:

    def f(a, L=[]):
        L.append(a)
        return L

In this example, `a` is a mandatory parameter and `L` is an optional parameter because it is defaulted as an empty list.  So, this function appends `a` to a list `L`. This list `L` is then returned to the caller. If a list is not passed to the function, then the function creates a new list to be populated. This list's lifetime is that of the program, but its scope is strict to the function. 

*Important Warning* If you use the default parameter list, it is created only ONCE and is continually populated each time you use it. For example, if we called:

    b = [1, 2, 3]
    f(4)
    f(5, b)
    f(5)

The function would return the following after each call:

    [4]            #this is the default parameter list
    [1, 2, 3, 4]   #this is list b
    [4, 5]         #this is the default parameter list again

Now, if our function was instead:

    def f(a, L=None):
        if L is None:
            L = []
        L.append(a)
        return L

The default scoped value of `L` would be `None` so `L` on each iteration would return either a new list with the appended value or the passed list with an added value. This is a way to guarantee variable sanity and to avoid sharing a variable between function calls if you don't want.

A final note goes to those programmers with experience in C or Java-like languages. Python does not support function overloading. This means you cannot write two functions with the same name to handle the same task for different inputs. In Python, it is preferred that you use default parameters to control the overload. If you have more questions, I recommend reading the Python API but feel free to ask questions here.

Have fun all and see you next week with more advanced function calling features.