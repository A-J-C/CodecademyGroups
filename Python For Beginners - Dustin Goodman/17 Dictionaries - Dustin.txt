I realize this is coming rather late down the line, but I thought it would important to finally review dictionaries. Dictionaries are a special built in data structure in Python. For those of you coming from other languages, dictionaries are also known as hash tables. Like a real dictionary, Python dictionaries have a look up value, called a key, that point to a defined value or object, called a value. Dicitioanries are great for grouping like data together in a single object that is also iterable, like an array. Unlike arrays, dictionaries are not ordered so you cannot expect an alphabetically sorted list when iterating the table.

Like any other class, dictionaries have a wide variety of built in methods which we'll review today. To begin, let's learn how to create a dictionary. There are two ways to define an empty dictionary. We can either call the class constructor or, like arrays, build the dictionary immediately.

    #dictionary constructor method
    x = dict()

    #quick constructor method
    y = {}

The quick constructor also allows you to fill in static elements that you'll want in your dictionary. So, we could have defined `y` to be:

    y = {'milk':1.99, 'cereal':2.99, 'juice':1.59}

Now, we have an awesome dictionary to test our methods. Two methods in dictionaries that are especially important are the `keys()` and `values()` methods. `keys()` returns a list of all the keys in a dictionary in no particular order. `values` returns the values in a dictionary in the same order `keys()` returns. Here's an example output from calling `keys()` and `values()` on our dictionary `y`.

    #calling keys on dictionary
    y.keys()
    #output: ['juice', 'milk', 'cereal']

    #calling values on dictionary
    y.values()
    #output: [1.59, 1.99, 2.99]

You can also iterate a dictionary in the following way:

    for key in y:
    	print key, y[key]

This would output:

    juice 1.59
    milk 1.99
    cereal 2.99

When you iterate a dictionary, your iterator takes on the value of the keys as if you called `keys()` on your dictionary which can then be used to access each value in the dictionary. Recall earlier that I said that dictionaries are not ordered. Notice that my construction of `y` does not match the output from iteration. If you wanted to iterate a dictionary in a particular order, you would have to get the list of keys and manipulate the order of it to output in your desired order. If I wanted to print my dictionary `y` in key alphabetical order, I could do the following:

    iter = y.keys().sort() #use the list sort method
    for k in iter:         #use the sorted key list to iterate dictionary
    	print k, y[k]      #print key and value

If you want to change or add a new element to a dictionary, you would do the following:

    y['bread'] = 3.99
    #output: {'milk':1.99, 'cereal':2.99, 'juice':1.59, 'bread':3.99}

Note, the order I created was random and does not reflect what your interpreter would output. If you want to delete an element, you would call `del y['milk']`. If you want to test for the existence of a key in your dictionary, you could write `'cereal' in y` which would return a boolean whether or not the key existed. Similarly, you could write `'milk' not in y` to see if a key was not in the dictionary. There are several other dictionary methods which you can use but these are the base set that will let you do most operations you need to do. For a full list of dictionary methods, see the Python documentation at http://docs.python.org/2/library/stdtypes.html#typesmapping.

That's it for this week. Happy April Fools!
