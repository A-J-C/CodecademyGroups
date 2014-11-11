So far, we’ve been mainly focusing on skills that will help you write Python code which is good in all, but it’s also nice to have some tools to help you communicate with non-Python programmers. Thus, there is a high level language called pseudocode that allows you to write how a “process” or “procedure” should be written in “plain” language. There’s some bad news though. There is no standard for how you write pseudocode. Every programmer has their own way of writing pseudocode based on the language they are most accustomed. Hence, we’re going to talk about some buzzwords and some syntax styles that you may or may not be familiar with. I’m going to list a few processes that you can do in every language and similar keywords or some symbols that you might find depending on the writer of the pseudocode. At the end, I’m going to write a “complex” pseudocode example and translate it into Python.

**assignment** - The most important feature in almost every language is assignment. Depending on how people choose to deal with the equality operator, they’re going to represent this in one of two ways, which are `=` and `:=`.

**arithmetic operators** - Typically people will use your typical arithmetic operators such as `>`, `<`, etc. However, rather than using `==`, people will usually write `=` like you would using math notation. The last option is actually writing out the options. So some might write, `x equal to y` or `x greater than y`. The tricky one in this case is the inequality symbol. I’ve seen people use `!=`, `not =`, and `<>`. Just pay attention to the context and you should be able to figure out what’s going on.

**boolean operators** - Typically for these, people will use the word version rather than the symbolic versions so `&&` (used in JavaScript and other languages) will be `and` which is what we use in Python. This will be the easiest translation.

**conditional statements** - Usually people will write `if`, `else if`, and `else` to begin the statements. Then, they’ll write the condition followed by `then`. Finally, they’ll write the code block and end the block with `end`. Here’s a quick example:

    if x is greater than max then
        call switch x and max #I’ll explain this in a second.
    end

**function definition** - Depending on the language you are reading, there are several choice words defining the beginning of a function. `procedure`, ‘process`, and `function` are the main ones that come to mind but you might find other words that define a short set of operations.

**function calling** - This is also fairly conditional on the language. Some people will write a function call like you would in whatever language they’re accustomed to while others will describe the function. In the above example, I chose to describe the action. The `call` keyword is a great indicator that someone is describing a function. It is important to note that since pseudocode can be written at various levels of abstraction, one could think of writing descriptive functions calls without specifying the pseudocode for the function, leaving it as a problem to be solved in implementation.

**loops** - Loops are going to be very similar to conditional statements but instead of `then` they use `do`

So these are the main key words and phrases to keep an eye on. Below is an example of some pseudocode for FizzBuzz.

    function fizzbuzz(n)
        for i in range 1 to n do
            if i is divisible by 3 and 5 then
                print “FizzBuzz”
            else if  i is divisible by 3 then
                print “Fizz”
            else if  i is divisible by 5 then
                print “Buzz”
            else
                 print i
            print newline
        end
    end_function

    call fizzbuzz with 100

Which translates to in Python as:

    def fizzbuzz(n):
        for i in xrange(1,n+1):
            if i%3 == 0 and i%5 == 0:
                print “FizzBuzz”
            elif i%3 == 0:
                print “Fizz”
            elif i%5 == 0:
                print “Buzz”
            else:
                print i
        print ‘\n’

    fizzbuzz(100)

Enjoy!
