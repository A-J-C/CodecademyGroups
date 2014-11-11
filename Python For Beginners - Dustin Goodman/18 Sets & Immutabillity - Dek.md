Today we're going to talk about `set`s, a data structure that I mistakenly covered in
[Week 14 review](http://www.codecademy.com/groups/python-fro-beginners/discussions/513db1703a03bbfc0b0006f2) being under the impression that it was the topic of one the lessons in the Python track. In fact it isn't, but it should since it's a nicely useful object. So this will be a new topic for many of you and, inevitably, a long one.

A Python **set** is very close to the mathematical set: it can store many objects, but they must all be _unique_ and they're not stored in any particular _order_ or sequence. Let's start with **uniqueness**, and we'll tackle the ordering later.

While you are used to store the same value multiple times in a list (es. fibonacci = [1,1,2,3,5]) this is not possible with sets: you can only have one copy. Let's try and define a set in the Python console:

    > fibo = {1, 1, 2, 3, 5}
    > print fibo
    => set([1, 2, 3, 5])
    
The `{}` is the literal notation for sets. As you might remember from last week, it's also the notation for dictionaries, but Python is smart enough to distinguish between the two. An exception here is the empty literal `{}` which will always evaluate to a dictionary.

As an alternative you can use the constructor method:

    empty = set()
    fibo = set([1, 1, 2, 3, 5])

The constructor accepts any kind of iterable object: you can pass a list, for example, and the resulting set will have all the elements in the original list but with duplicates removed.

In the `fibo` example, we tried to store the first 5 elements in the fibonacci sequence, but we only got four: that's because Python only stored one instance of the number `1`. But let's go by the manual.

The [manual](http://docs.python.org/2/library/stdtypes.html#set) says that a **set** is an _unordered_ _collection_ of _distinct_ _hashable_ objects. Let's break this down.

What is a **collection**? We already saw other examples: the [list](http://www.codecademy.com/groups/python-fro-beginners/discussions/50bcc8cde3a02329b9000003) and the [dictionary](http://www.codecademy.com/groups/python-fro-beginners/discussions/5159a72318e52a0dd9001a6a). What
these structures have in common is the fact that they store multiple values.

What about **unordered**? One difference between lists and dictionaries was that lists are sequence of values with a defined order, while dictionaries not, simple as that. As the definition implies, sets are also lacking an order relationship between their elements:

    > standings = {"Achilles", "tortoise"}
    > print standings
    => set(['tortoise', 'Achilles'])

As a consequence, two lists with the same elements in a different order are considered different

    > ["a","b"] == ["b","a"]
    => False

while a set is only defined by the elements it contains, not by their order:

    > {"a","b"} == {"b","a"}
    => True

We already saw what distinct means with the Fibonacci sequence. We'll get back to the hashable part soon. Let's first see what we can do with a set.

We can add elements to it:

    > standings.add("turtle")
    
remove them:

    > standings.remove("tortoise")

get the cardinality (length):

    > print len(standings)
    
check for membership (presence) of elements:

    > print "Achilles" in standings
    => True
    > print "Zeno" not in standings
    => True    
    
and iterate over them:

    > for name in standings: print name
    
Also, you can use **set comprehensions** to define a set, using the same rules that apply to [list comprehensions](http://www.codecademy.com/groups/python-fro-beginners/discussions/50cf63f7bc3b636c4500001d) except for the use of the curly braces:

    > squares = {x**2 for x in range(10)}

Last but not least, set operations (subset, superset, union, intersection and difference) are defined. More about it later.

Now, what does **hashable** mean? Well, an object is hashable if Python knows how to evaluate a _hash value_ for it. Not very helpful, I know. Let me take the panoramic route here...

In Italy, the equivalent of the [Social Security Number](http://en.wikipedia.org/wiki/Social_Security_number) is called [fiscal code](http://en.wikipedia.org/wiki/Italian_fiscal_code_card): rather than being just a number, it is comprised of three letters from your first name (consonants first, then vowels), three from your last name, a sequence based on your birth date, a code corresponding to your birth place. For **Guido von Rossum**, it would be:

    VNR GDU 56A31 BDFLF
    
(where I made the part about the birth place up since the codes are only defined for italian cities.) Now, it's obvious that if we have two different fiscal codes, they must belong to two different persons. Also, it's almost impossible that two persons have the same fiscal code.

And that's exactly what a **hash value** is: a "digest" of the object that can be used to identify it and distinguish it from the others. You don't need to verify that each part of object X is equal (or not) to each part of object Y: you just compare the two hash values.

    > "Guido von Rossum".__hash__()
    => 1036986244

With a good formula for hash values, the occurrence of two different objects having the same hash (called "collision") is very unlikely. This property allows us, as we saw in [Week 14](http://www.codecademy.com/groups/python-fro-beginners/discussions/513db1703a03bbfc0b0006f2), to implement very (very very very) fast search algorithms.

But it comes with a price. In order to be meaningful, the hash value must be defined on properties that are not likely to change: I might dream about being born in the 60s in California, but that's not gonna happen, and therefore my fiscal code will always stay the same.

Back to Python, hashable objects are supposed to be **immutable**: once created they stay the same for all their lifetime. While this is not enforced by Python for your custom object, it is true for the built-in ones.

So, sets can only contain immutable objects. And since a set is not itself immutable (I can add and remove objects) I'd expect that I won't be able to add a set inside another set:

    >   fable = {"tortoise", "hare"}
    >   paradox = {"Achilles", "tortoise"}
    >   fable.add(paradox)
    Traceback (most recent call last):
      File "<stdin>", line 1, in <module>
    TypeError: unhashable type: 'set'
    
and this is a major difference with mathematical sets. (Don't despair! For the math nerds amongst you, Python provides the `frozenset()` constructor to create immutable sets!)

But... what if what I actually wanted to do was just adding all the elements from one set into another? Well, that's what the `union` was for:

    > fable = fable.union(paradox)
    => set(['Achilles', 'hare', 'tortoise'])
    
and in fact, being so common, Python defines the `|` operator as a shortcut:

    > fable = fable | paradox
    => set(['Achilles', 'hare', 'tortoise'])

and the compound operator `|=` can be used in a similar fashion to `+=` for an even shorter notation:

    > fable |= paradox
    => set(['Achilles', 'hare', 'tortoise'])
    
When the elements to add are in an iterable that is not a set, i.e. a list, we can use the update method:

     > menu = {"spam", "spam egg sausage and spam", "egg bacon and spam"}
     > menulist = ["spam", "lovely spam", "lovely spam"]
     > menu.update(menulist)
     > menu
     => set(['lovely spam', 'spam egg sausage and spam', 'egg bacon and spam', 'spam'])

Operators are also defined for other methods: `-` for the difference (a - b = all elements that are in a but not in b), `&` for the intersection (a & b = all elements that are both in a and b) and `^` for the symmetric difference (a ^ b = all elements that are either in a or in b but not in both).

    > print menu & set(menulist) # What they have in common
    => set(['spam'])
    > print menu - set(menulist) # What is different
    => set(['spam egg sausage and spam', 'egg bacon and spam'])

And that's [more than enough](http://www.youtube.com/watch?v=anwy2MPT5RE) about sets. Stay tuned for our weekly challenge.

-----------------

P.S. Some technicalities. What I described refers to Python 2.7.x as well as Python 3.x.x

The set was first introduced in Python 2.3 as a library (you had to `import sets`, plural, in order to be able to use it in your programs). In Python 2.6 `sets` was replaced by `set` , a built-in type, that is part of the Python language (while the old library has been deprecated). Only with Python 2.7 the `{}` notation and the comprehension were introduced.

So, you won't be able to use curly brackets literals in some online IDEs that are still stuck to older versions of Python, and you may even have to `import sets` if the version is Python 2.5 or earlier. To check which version of Python is running, use:

    import sys
    print sys.version

For Python 3 users, same as Python 2.7 applies except that obviously the old `sets` has been removed for good.