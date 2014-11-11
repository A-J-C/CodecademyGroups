Week 29: Iterating in Python
======================

This week I'll cover some of the built-in functions that make writing loops in Python as easy as 3.14

Sorting
-------

Let's start with a simple one: what if my list is not sorted but I want to print it in alphabetical order? I could certainly call the `.sort()` method on my list and then print it, but that method works in place. This means that my list will actually get sorted, and perhaps I don't want  it. In fact, perhaps I don't even want to store a new list which I'm not going to need anymore as soon as I `print`ed it.

And moreover: what if I don't have a list at all? What if I have a [set](http://www.codecademy.com/groups/python-fro-beginners/discussions/5162b5c657ca7497640043b1)?
The Python way is to use [`sorted()`](http://docs.python.org/2/library/functions.html#sorted). It works with any iterable object, not just lists.

    a = {"a", "b", 1} # A set, not a list!
    print a
    try:
        a.sort()
    except:
        # Sets don't have a sort method!!!
        print sorted(a)
    for stuff in sorted(a, reverse=True):
        print stuff

Reversing
---------

See what I did there? By specifying the [named parameter](http://www.codecademy.com/groups/python-fro-beginners/discussions/5150818eade0674d310044e6) `reverse` you can also get reverse order. But what if my list (let's get back to lists) is already ordered. It would be a waste to call `sorted` just to reverse it, right?

Enter, [`reversed`](http://docs.python.org/2/library/functions.html#reversed):

    a_to_z = ["a", "to", "z"]
    for s in reversed(a_to_z):
        print s

Once again, after I used it the new reversed list is gone, unless I store it in a variable.

Zipping
-------

Now, let's say that I have two lists of strings, names and verbs, and I want to print them in random couples just for fun. Since the for loop only allows me to iterate over one iterable object, I would think that the only way is to write something like:

    from random import shuffle
    
    verbs = ["kill", "kiss", "marry"]
    nouns = ["Joe", "Jane", "Guido"]
    shuffle(nouns)
    
    for index in range(len(verbs)): # <- not zen!
        print str(index+1)+".", verbs[index], nouns[index]
        
I would be wrong: always bet on Python when you need to write better and/or less code! It's indeed true that I can't loop over two or more iterables at the same time. But I can loop over a list of tuples. All I need is a way to build a list of tuples like:

    # Your list will be different because of shuffle
    [("kill", "Joe"), ("kiss", "Jane"), ("marry", "Guido")]
    
which is exactly what the [`zip()`](http://docs.python.org/2/library/functions.html#zip) function does!

    from random import shuffle
    
    verbs = ["kill", "kiss", "marry"]
    nouns = ["Joe", "Jane", "Guido"]
    shuffle(nouns)
    
    for verb, noun in zip(verbs, nouns):
        print verb, noun
        
Notice that zip will work with more than two lists, and even if the lists are not of the same size. In the latter case, the iteration will stop when the smaller list reaches its end.

Enumerating
-----------

Yes but... My "non zen" code printed a nice ordered list. How do I get that with zip? Well, you don't. But that doesn't mean that you're back at iterating with `range`! What you need is [`enumerate`](http://docs.python.org/2/library/functions.html#enumerate):

    # Let's start with verbs only
    verbs = ["kill", "kiss", "marry"]
    
    for index, verb in enumerate(verbs, start=1):
        print str(index)+".", verb
        
As you can see, enumerate returns a tuple like zip: the second element will store the currently iterated element while the first one is the index of that element, or better: a counter. As you can see, with the named parameter `start` we were able to start counting at `1` even though all elements in list have been printed. (That is, enumerate didn't start at index 1: it just started counting at 1.)

Now, how do we get a zip/enumerate combo? That's tricky. Since `zip(verbs, nouns)` would return a tuple, like `("Marry", "Guido")`, then calling `enumerate(zip(verbs, nouns))` will return a tuple inside a tuple, like:
     
    (3, ("Marry", "Guido"))
    
and therefore, it would not match `index, verb, noun`: Python will complain that there are three variables, but only two values: a number and a tuple. You need to write the for loop like this:

    from random import shuffle
    
    verbs = ["kill", "kiss", "marry"]
    nouns = ["Joe", "Jane", "Guido"]
    shuffle(nouns)
    
    for index, (verb, noun) in enumerate(zip(verbs, nouns), start=1): # <- See?
        print str(index)+".", verb, noun
        
Notice the parentheses around `verb` and `noun`: Python will take the inner tuple `("Marry", "Guido")` and unpack it, storing the first value in the first variable and the second in the second variable.
(I'm not aware of any simple built-in function that would allow you to spare the parentheses, but there might well be one. We're talking Python after all...)

Wrapping Up
-----------

These all seem overkill for such a simple example, but for longer loops, it'll make your code much cleaner. If your needs are more exotic than these functions can handle, then take a look at the [itertools](http://docs.python.org/2/library/itertools.html) module.
