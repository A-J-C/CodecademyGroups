Hello, I’m Hobo. This will be my first time, but I’ll be doing this weeks lesson. For this week the topic will be diverged from Objects in favor of a more pressing subject: *Whitespace and Indentation.*

I’m sure that most of us here have looked at the Q&A section of the Python courses, either on Codecademy or any other website as such. If you have been to that section, you’ve probably seen many of the *“Why does my code not work?”* topics, which would have replies based on flaws or possible flaws. If you have indeed seen these topics, you’ll probably be very familiar with the phrases “*Did you indent your code properly?*” or “*Indent your code.*” Well, this is the topic of todays discussion.

Let’s take a look at what we mean when we say *“Indentation”*.

To start off, we are going to have a little talk about the concept *“Code Blocks”*.

In regard to code, a *block* is a section of code which is grouped together. Blocks consist of one or more declarations and statements. A programming language that permits the creation of blocks, including blocks nested within other blocks, is called a block structured programming language:

    if x == 3:
        #block of code would start here
        x += x       
        y = x ** 2
        print y
    #block of code would end here
    else:
        #block of code would start here
        print “cakes”
    #block of code would end here

As you can see in the above example of an `IF statement`, I have used comments to show you where the block of code starts and ends. In this statement, the condition to be met is `x == 3`, meaning if the variable `x` *is equal to 3*, then the condition will evaluate as `True`. That would start off the first block and run the following lines of code, ending with a number showing up on the screen. *If `x` does not equal three*, the condition is therefore `False` and will fall under the `else` section of the statement. In that case, it runs a different block of code that prints the word `cakes`.

Now, as you can see there is a stark difference between the positioning of the code before and after the blocks of code, when compared to the blocks themselves. This is where we begin talking about Indentation. Take a look at the examples below and see if you can see an issue:

    if x == 3:
    print “cake”
    else:
    print “cakes”

The above chunk of code cannot be copied and pasted into the Python interpreter to be run because it has an egregious syntax error. It's missing indentations! Lets show another example where indentations are made:

    if x == 3:
        print “cake”
    else:
        print “cakes”

Now when you look above, you can see there is a sizable gap between particular lines of code and the page margin, this is Indentation. To make an indent you press the -Tab- key to form a gap between the far left side of the page and the beginning of the text.

Now, you’ve seen what Indentation looks like but that didn’t really tell you why it was so important.  If you’ve come from other programming languages, you’ve probably noticed that those languages don’t function with whitespace and indents but favor another way of separating code blocks. These languages use the semicolon `;` and curly brackets `{}` to delimit code, but Python has opted to use white spaces and indentation in place of this convention.(**)

All of the examples shown and this discussion about Whitespace and Indentation are about Formatting the code. This formatting is used to allow the Python interpreter to read what we're writing.

White space is generally just as it sounds, a blank space in the text that does absolutely nothing. When you indent your code, you have a gap of white space. What does this empty area do? It tells the program that a line of code has ended, therefore showing when a new line has begun. The amount of white space provides information on when it will run. In some cases, it is referred to as ‘Indenting’.(****)

Now, if you remember earlier we started this topic off by talking a little about *Code Blocks*. Let’s continue talking about it now. When you indent your code, you are showing the computer the difference between code and blocks of code. Remember, a block of code is a set of lines that define what happens when a condition is met. With each level of an indent we show different a block of code. What does the *white space* do? It helps us to separate two completely different blocks from one another.

Similarly, Indentation is Pythons view of curly brackets. Python can see when code is indented which means it is a part of the previous *function*. If you *defined* a function and wanted to run it, Python would know which code was supposed to run based on the indents placed (These indents show it where the specified block of code starts). It would also know that when the indents stop that the particular block of code has ended and so it does not need to run it anymore:

    def cake():
        #block of code starts.
        code here
        code here
        code here

The above is a mere example. When the indent ends and there is a line of white space, the program knows “Okay, that block of code has ended so lets go back to where we were before and continue running this program.” If we didn’t have a proper indent then that would confuse the computer about what it should or shouldn’t run and when it should run it.

I would like to make sure everybody is clear that Python has some specific Indent sizes it will or will not accept. Be wary of those. Some programs (IDLE for instance) will have a predetermined indent size that works with Python. The Ideal indent size for Python should use 4 spaces. (The same as hitting your space key four times.)

Also, while you must remember to indent your code. Don’t forget to avoid indenting it too much, or putting them in unnecessarily. Python wants them done in a specific way and if we fail to do so it will end in a syntax error.

To summarise, Indenting is an important part of Python. Indents explain to the compiler when a block of code starts and ends. The way you indent and the place you indent will affect the program in different ways based on how the compiler interprets it.
Well, thats all for this week. Thanks for reading.


----------


****** Footnotes


----------


(**)Now, for those of you unfamiliar with the aforementioned Semi-colon and Curly brackets, you probably want some clarification towards how they are similar to Whitespace and Indentation:

    if (x == 3)                             #The IF Statement
    {                                #Opening Curly Bracket
    console.log("True");                        #Output (Ends with Semi colon)
    }                                #Closing Curly Bracket
    else
    {                                #Opening Curly Bracket
    console.log("False");                    #Output (Ends with Semi colon)
    }                                #Closing Curly Bracket

Now, you don’t need to know or understand the above statement, that is a section of code taken from JavaScript. The key part of that example to look at is first, the ‘Semi-colon’ at the end of some of the lines. That symbol is used to tell the program “This line of code ends here!” therefore allowing the computer to move on to the next line to begin something else. Similarly, Python doesn’t have a semi colon for ending its lines, but it does have White space.


----------


(****)Why is Indenting important you ask? Very simply, look again at the above example taken from JavaScript. See those curly brackets? The curly brackets exist to show the program what lines of code should only run during that If statement or its corresponding else statement. If it wasn’t for those curly brackets the program may run any code.
Remember, when a program reads your code and runs it, it always starts from the top of the code and makes its way down. What would happen if we didn’t have those curly brackets? Very simply:

    If (x==3)                        # This line will start the if statement.
    console.log("True");                    # This line merely displays text.
    else                            ### As you’ve seen, this time there are no curly brackets. In this program the reader would read the code, it would run the if statement. It would see the output. That would be where it errors, while it may run the output because it immediately follows the statement, the program cannot differentiate between code that should run if the statement is True or code it shouldn’t run altogether. The program would reach the else statement and merely go “What is this? This shouldn’t be here! I can’t run this from inside an IF statement!” before it stops functioning.

