Howdy folks! I'm back again to bring to you this weeks lesson on Control Statements. It was recently noted to me that I completely skipped this topic and thought it would be crucial to discuss it this week. So let's get started!

One of the most important programming concepts is that of [Control Flow][1]. Control flow lets us determine which instructions our programs should run upon execution. In Python, we have `if...else` statements to perform this type of logic. Let's look an example. Let's say we want to write a function that divides even numbers by 2 and multiplies odds by 3. The code would like as follows:

    def f(x):
        if x%2 == 0:
            return x/2
        else:
            return x*3

A couple of very important notes to make about `if...else` statements. `if` statements require a [boolean expression][2] (we'll review this next week) in order to produce the control flow. Note how it looks a lot like a function header in that it has a colon, `:`, after the boolean expression and then a new block on the next line. Note the new block is indented. The way you know you've ended your `if` statement is when you exit your indented block. (See how important proper indented code is now?) Unlike the `if` statement, the `else` does not take a boolean expression. This is because the `else` statement performs on any case not evaluated to `true` in the `if` statement. It is also important to note that `else` statements are completely optional. If you don't need the `else` don't use the `else`. ;)

    if expression:
        #if expression is true, run this code
    else:
       #if expression is false, run this code

Above is the syntax and an example of how the above clause works. There is one more thing to tell you about. There is another control statement called `elif` which is short for `else if`. If you write `else if` you will cause a compiler error and your code will not run, use `elif`. `elif` lets you add more control to your program. Let's say in our above function, we first wanted to make sure that our input was above 0. We could use an `elif` statement to restructure our code to handle the case as follows:

    def f(x):
        if x <= 0:
            return 0
        elif x%2 == 0:
            return x/2
        else:
            return x*3

See how easy that was to do? Another note is you can embed control statements inside other control statements or loops. Go write some code now and see how many times you find yourself needing control flow.

That's it for this week. If you guys have a topic you would like to see covered, please don't hesitate to [email me][3] or shoot me a message on [Twitter][4]. See you next week!


  [1]: http://en.wikipedia.org/wiki/Control_flow
  [2]: http://en.wikipedia.org/wiki/Boolean_expression
  [3]: http://sharocko@gmail.com
  [4]: http://twitter.com/thesharocko