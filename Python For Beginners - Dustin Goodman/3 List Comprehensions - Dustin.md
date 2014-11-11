This is a fun topic that distinguishes the professional Python programmers from the Python novices. Bare with me through this one because it is very math involved.

In mathematics, we define sets (aka lists) in various ways. Here are a few for example:

    S = {x² : x in {0 ... 9}}
    V = (1, 2, 4, 8, ..., 2¹²)
    M = {x | x in S and x even}

Just glimpsing at these examples, we can think of ways to write them in Python. A novice programmer might make the naive approach and write the first example as follows:

    S = []
    for i in range(0,10):
        S.append(i**2)

However, with list comprehensions, we can write more elegant one liners that look almost identical to the original math notation. Here are our original examples in Python list comprehensions:

    S = [x**2 for x in range(10)]
    V = [2**i for i in range(13)]
    M = [x for x in S if x % 2 == 0]

I'm now going to write out in plain English what each example does:

 1. Square each value x for x in the range 0 to 9.
 2. Raise 2 to the ith power for i in the range 0 to 12.
 3. Add x to the lift for every item in S that is divisible by 2.

Pretty cool, right? Here's the basic syntax for all your list comprehensions:

`x = [<operation> for <variable> in <list/range> <optional condition>]`

So set an operation like `2**i` then create a for loop to define what items will go into the list and finally add a conditional if you think it's necessary.

That's it for this week. Ask questions if you're still confused and feel free to email me if you would like to lead a review.

Credit for the above examples courtesy of http://www.secnetix.de/olli/Python/list_comprehensions.hawk 