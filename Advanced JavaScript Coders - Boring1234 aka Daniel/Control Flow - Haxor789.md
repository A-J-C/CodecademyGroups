Extended version of this:
http://www.codecademy.com/de/forum_questions/52373a75548c3515940000dc

 - Control Flow  Part 1

Untill now your code has been statements executed from top to bottom. In this review we'll cover one of the most basic but powerfull tools to change this: **conditional statements**! These statement such as:

- if statements
- if-else statements
- if-else if-else statements

give you literally the option if or if not code is executed and what should be done else.

The most simple conditional statement (1) looks like this:

    if(condition)
       statement;

Here statement is exactly 1 statement that gets evaluated **if** the condition is `true`. The condition could be anything that has or evaluates to a boolean value. Common choices are comparisions like `a<b`,`a>b`,`a<=b`,`a>=b`, `a==b` ,`a===b` or `a!=b`, `a!==b` but also variables (their values) can be used, just make sure you know what value is [truthy or falsy](http://www.sitepoint.com/javascript-truthy-falsy/). In case you want an alternativ to the if you can extend it with an else (2):

    if(condition)
       statement;
    else
       statement2;

Now if the condition is `false` it would execute the stuff after else. Again statement and statement2 are only one statement (each).

 *But what about using more than one statement in a case?* (3)

    if(condition)
       statement1;
       statement2;

here statement1 would belong to the condition and statement2 would be executed without condition. (4)

    if(condition)
       statement1;
       statement2;
    else
       statement3;

And here it would get even worse, as the else needs to follow directly after the statement of the if or they will not be treated as connected and you get an error as an else doesn't make sense without an if.

*So how can we use more than one statement per case, what are these {} we usually use and why should we even bother about these cases mentioned above?*

Well to have more than one statement per case we use the trick of working with blocks of code which start with { and end with } these blocks count as one statement regardless of the number of statements which are inside.(\*)

The reason why we should have a look at this although you could be perfectly fine by using blocks all the time even if they are not necessary is that we every now an then may encounter one of the errors described above which are related to this ability.

e.g. a semicolon:
When you put a semicolon at the end of a condition, like this: 
    
    if (condition);

some may think this ends the conditional statement and the following code is processed without regard for the outcome of the conditon.

That's pretty close, but the semicolon doesn't end the if statement itself, it ends the statement of the if. This might be confusing, but have a look at (1) and you could see that `if(condition);` just means:

    if(condition)
      /*empty space*/;

so the semicolon creates an empty statement by ending the "nothing" after the condition which would normaly be ignored and now the condition is either finished or an else needs to follow directly after it, but mostly it was just a mistake and it goes like this: `if(condition);{...}` and then you end up at the error described in (4).

So we handled the if, the if-else and a really common bug and it's origin. But what if we want to split up in more than two directions.

Well we could nest conditional statements:

    if(condition)
       statement;
    else{
       if(condition)
           statement;
       else{
          if(condition)
             statement;
          else
             statement2;
        }
    }

But as you can see even with indentions the code becomes less readable when adding more and more levels of nesting. Here we can use that conditional statements itself count as one statement, which makes sense as no matter which way you choose at most one statement (or something that counts as one) is executed, which helps us to make it more readable (5):

    if(condition)
      statement;
    else
      if(condition2)
        statement2;
      else
        statement3;

could be formatted to:

    if(condition)
      statement1;
    else if(condition2)
      statement2;
    else
      statement3;

Now you're still on the same level and although **else if** is technically just nesting a conditional statement in the else case of the original if-else it looks pretty intuitive and as you can nest as many statements as you like this enables us to branch out to far more than 1 or 2 options.

<sub>(\*): {} are used as blocks of codes for conditions and loops, functions and objects may use them in a different way.</sub>

[Return To Master Menu](http://www.codecademy.com/groups/advanced-javascript-coders/discussions/53307af3631fe9e8de00103b#discussion-53307af3631fe9e8de00103b)