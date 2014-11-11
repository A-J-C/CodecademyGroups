This week we're going to discuss a very powerful, yet very dangerous function called `eval`. `eval` lets you `eval`uate code and execute it from user input. "That's so cool!" some of you might be thinking, but you should really be thinking, "That's really scary!" Indeed, you should be scared of `eval` but sometimes it is helpful to use it. To get in my cheesy quote of the day, "With great power comes great responsibility."

The following is a quick and very bad implementation of a script using `eval`:

    x = raw_input("Give me some input... ")
    print eval(x)

If you were to write a valid Python expression like `x+1` or `sorted([1,5,2])`, it would evaluate correctly. However, if you wrote something like `abc`, you would get a NameError because the program doesn't have a variable `abc` defined. However, this isn't even the worst of what could go wrong. The above problem could be fixed with a simple `try...except` block which we learned about already. The real danger lies in when we have private information or other functions we don't want the user to call.

Yes, you heard me correct... `eval` gives the user FULL access to your script. Fortunately, `eval` is shipped with two additional paramters, i.e. `eval(expression[, globals[, locals]])`. These are dictionaries that define which global and local functions your user can call using `eval`. Unfortunately, my explanation of how to make a valid dictionary with calls won't be nearly as elegant as my resource's explanation so I'll allow it to better explain the rest. You can find the article at http://lybniz2.sourceforge.net/safeeval.html

Enjoy!