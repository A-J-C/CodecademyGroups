So I apologize now but this review is possibly going to be lengthier than my usual reviews. There are a lot of boolean expressions to cover and so much to say about them.

There are two main sets of boolean expressions that we use in Python: logical operators and comparison operators. Logical operators are words we use almost every day like `and`, `or`, and `not`. Boolean operators compare objects based on certain properties. In this lesson, I'm going to teach the *best practices* for using boolean operators. Python allows you to use some weird syntaxes, but they are **not** portable to other languages therefore I will not teach these methods.

**Logical Operators**
Logical operators are used to compare different booleans, i.e. `True` and `False`. The output of a comparison operator is also a boolean. So, how do we use these logical operators? Well, we just write the sentences we want to test. Here are some examples of the 3 logical operators.

    True and False   #this will be False
    True or False    #this will be True
    not True         #this will be false

All of these operators are called "short-circuit" operators. This means that they test the minimum number of expressions needed to be either `True` or `False`. This means we try to put the case that would drive our logic faster in the first position. You'll see what I mean in a second. Another note, if you're familiar with other languages you might be used to using `&&`, `||` and `!` or `~`. Do not use these in Python. They don't work and in some cases have different meanings.

The `and` operator requires all associated terms be evaluated to `True` in order to be `True`. If a single operator is `False`, then `and` evaluates to `false`. In our above example, the `and` statement sees `True` and continues to evaluate the `False` which forces the `and` to `False`. If the order had been `False and True`, the `and` statement would have evaluated to `False` immediately upon finding the `False` statement and would never test the `True` case. Hence, it would be best to put `False` before `True` so the `and` statement doesn't test the `True` because the `False` drives it `False`.

The `or` operator requires one or more associated terms be evaluated to `True` in order to be `True`. In our above example, the `or` statement will evaluate to `True` immediately because it is the first of the statements and it meets the minimum requirement for `or` to be `True`. Therefore, the `False` case is never tested.

Unlike the other two logical operators, `not` is a unary (single input) operator whereas `and` and `or` are binary (two input) operators. The `not` operator takes in an argument and returns its logical operator. Therefore, `True` becomes `False` and `False` becomes `True`.

(For those familiar with the exclusive or operator: It does exist in an abstract form and requires more detail than will be covered here today. If you want it sooner, post a comment and I'll show you.)

**Comparison Operators**
There are lots of comparison operators, and you're probably already familiar with them. The most common are `==`, `!=`, `>`, `>=`, `<=`, and `<`. The `>`, `>=`, `<=`, and `<` are numeric comparisons. These operators work on other objects but they produce weird results, so only use them on numeric types. `==` and `!=` are used to test if two objects are equal to or not equal to each other. Do not use `=` to test for equality, you'll accidentally reassign a value. These operators all return either `True` or `False` therefore you can use them with logical operators to create good test cases. 

For instance, let's say you need to test if `x` is equal to `y` and `y` is less than 0. You could write `(x == y) and (y < 0)`. Notice how I used parentheses. These are not required but help my your statements easier to read and evaluate how you expect. There is a precedence of how these operators evaluate, i.e. `not` before `and`, but memorizing these orders is a waste of time if you use parentheses correctly.

That's it for this week. I know this is a lot of material but it's important and useful so review this often. Best of luck and have a good week folks!