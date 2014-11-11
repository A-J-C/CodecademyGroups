Hi! This week we’re going to talk about lambda functions and the `lambda` keyword.

Lambda functions (or lambdas) are regular Python functions that can be defined using a terser notation. You can use them every time a function is needed, and you can use a function every time a lambda is needed: they’re one and the same thing.

Since the `lambda` keyword doesn’t allow you to specify a name, lambdas are also known as **anonymous functions**. If you have ever dealt with JavaScript/jQuery, you probably used them a lot to deal with event callbacks. There are also other uses for them.

But let’s take a look at the syntax first.
You create a lambda by writing:

 - the keyword `lambda` followed by a space;
 - a list of arguments separated by commas, without the parentheses, followed by a colon;
 - an expression (and one only!) that is the value returned by the
   (lambda) function.

So, to declare a lambda to square a number, you write:

    lambda x : x*x

and to return the bigger of two strings:

    lambda s1,s2 : s1 if len(s1)>len(s2) else s2

Since lambdas have no name, it’s no use to create them like this: you won’t be able to call them!
An important difference between  `def` and `lambda` is that the former `def`ines a function, while the latter `return`s it: so you can assign the returned lambda to a variable or pass it as an argument to functions that expects other functions as arguments, which are at the base of **functional programming**. Let’s focus on these.

Let’s say we want to count how many times the number 6 is in a list. Easy:

    def count6_for(numbers):
       ret = 0
       for number in numbers:
           if number == 6:
               ret += 1
       return ret

Or, we can use functional programming, and namely the `filter` function. 

    filter (fil, l)

It takes two arguments: the second is a list, let’s call it `l`, while the first is a function, let’s call it `fil`, that takes an element of the list as an argument and returns a [Boolean](http://www.codecademy.com/groups/python-fro-beginners/discussions/5119149f64147035fb0006cb).
With `fil` we define a filter: it returns `False` for the elements of the list we want to get rid of, and `True` for the elements that we want to keep:

    def fil(el): # Return true for keepers, false for tossers
       if we_want_to_keep_this_element_in_l:
           keep_element = True
       else:
           keep_element = False
       return keep_element

When called, `filter` returns a new, filtered, list containing only some of the elements in `l`. Which ones? Again, if `el` is the generic element in the list, then, `el` is included in the filtered list if `fil(el)=True`.
So, to recap, we pass in an auxiliary function that returns a `True` or `False` and filter returns only those values that make that function True. It's important to note that `l` is *left untouched*: `filter` produces a new list rather than modifying the original.

Back to our example, we want to keep only the “6”s and get rid of everything else, so our `fil` function will be:

    def onlySixes(number):
       return number==6

We can then rewrite our function to filter the sixes and count them, like this:

    # This needs onlySixes() to work
    def count6_filter(numbers):
       filtered_list = filter(onlySixes, numbers)
       return len(filtered_list)

Since `filtered_list` contains only occurrences of the number `6`, we just returned the length of this list. But we had to define the `onlySixes` as a separate function that we'll probably never use anymore. Also: when reading the code, you need to search for the actual code of `onlySixes` to understand what `filter` does. This is where lambdas are convenient:

    # This doesn’t need onlySixes() to work!!!
    def count6_filter_lambda(numbers):
       filtered_list = filter(lambda x:x==6, numbers)
       return len(filtered_list)

No need to define `onlySixes` anymore: the function is defined as a lambda in the arguments we pass when calling `filter`.
Notice that this:

    filter(def filter6(number): return number==6, numbers)

won’t work, because, again, `def` is not an expression, it doesn’t return anything at all, not even `None`.

This wraps up our discussion about lambdas. Don’t forget to post questions, doubts, corrections and suggestions in the comments below. Also, if you’re interested in **functional programming**, let me know and I’ll start another thread on the topic.