Hello,
as announced, here it is:
The first review. :-)
I would like to establish weekly reviews here in this group, so you'll be able to review some topics, but you'll also be able to learn some new advanced concepts and keywords.
**Today's topic:** The Art of Looping.
You should have a basic understanding of loops, so this review will give you more information and keywords, which could be useful, when dealing with loops.
The structure of the review:
 1. `while` loops using Booleans to loop once
 2. The `break` statement
 3. The `continue` statement
 4. `break`ing an infinite `while` loop

So let's start. :-)

#### 1. `while` loops using Booleans to loop once

This one is here to refresh your knowledge about the `while` loop, as the same is [often used][1] in the ["Introduction to 'While' Loops in JS"][2] course.
I'll show you my example of the ["Solo flight"][3]:

    var soloLoop = function(){
      var bool = true;
      while(bool)
      {
          console.log("Looped once!");
          bool = false;
      }
    };    
    soloLoop();

As we can see, we just declare variable `bool` and assign a Boolean to it, so the (shorthand) condition evaluates to `true`. In the loop, we assign the other Boolean value to the variable `bool`, so the condition evaluates to `false` and the loop stops. Here we used `bool` as the condition, but we also could have used `!bool` as the condition and it would have to be the other way round:

    var soloLoop = function(){
      var bool = false;
      while(!bool)
      {
          console.log("Looped once!");
          bool = true;
      }
    };    
soloLoop();

That was just to refresh your knowledge, so let's learn something (probably) new:

#### 2. The `break` statement

The `break` statement allows you to stop the (current) loop.
So imagine, you have a loop, but while it is running, you realize, it has to stop. Well, usually it is too late then, or it is quite hard to make the program to stop the loop independently.
But there is a keyword, `break`, which allows you to stop the loop. You use it together with an `if` statement, which checks, if there is something other than the actual condition `true` and if there is, the loop will be stopped.
Some examples, one using a `for` loop, one using a `while` loop; both ought to count from `1` to `10`, but they stop at `5`:
1)

    for(i=1;i<=10;i++)
    {
    	console.log(i);
    	if(i===5)
    	{
    		break;
    	}
    }
2)

    var i = 1;
    while(i<=10)
    {
    	console.log(i);
    	if(i===5)
    	{
    		break;
    	}
    	i++;
    }

This is quite simple, isn't it? :-)
Time to learn another keyword:

#### 3. The `continue` statement

Imagine, you have a loop, which ought to print every number from `1` to `10` except `5`. You could use two loops, but it would be better to use one loop and to jump out of the loop, `continue`, if the iterator `i===5`. And, as you may have guessed, there is a `continue` keyword, which allows us to do this.
So instead of printing the number `if(n!==5)`, we can `continue` `if(n===5)`.
Again, two examples, one using a `for` loop and one using a `while` loop; both count from `1` to `10`, but they won't print the `5`:
1)

    for(i=1;i<=10;i++)
    {
    	if(i===5)
    	{
    		continue;
    	}
        console.log(i);
    }
2)

    var i = 1;
    while(i<=10)
    {
    	if(i===5)
    	{
    		i++;
    		continue;
    	}
    	console.log(i);
    	i++;
    }

This is quite doable; however, you have to restructure your code, if you convert your code from a `break` to a `continue`, especially, if you use `while` 
loops (compare the code above with this one to see what I mean), otherwise you could get an infinite loop.
Apropos infinite loops, there is one topic left:

#### 4. `break`ing an infinite `while` loop

The last topic is there to combine some concepts:
You know infinite loops are bad, as they crash your browser.
But maybe you'll find something like the following:

    var i = 1;
    while(true)
    {
    	console.log(i);
    	i++;
    	if(i>10)
    	{
    		break;
    	}
    }

This code prints the numbers from `1` to `10` to the console, although the condition never evaluates to `false`.
Well, actually it is not that hard: The condtition is always `true`, but `if` `i`, which is incremented again and again, is bigger than `10`, the loop stops.
So this is another method to write loops. :-)
This is definitely faster than a normal `while` loop and (probably) a *little* bit faster than a `for` loop, so this can be useful sometimes. ;-)

Okay, now you should have a basic understanding of (advanced) loops.

**Courses**
http://www.codecademy.com/de/courses/loops?curriculum_id=4f4b35445cb288000300000c
http://www.codecademy.com/de/courses/5085123dd3d87002000037f9 (Self advertisement :-P)

**Ending**
I hope you enjoyed this review and learned (at least) something. :-)
I would love to read feedback and suggestions.
Furthermore I need someone, who writes some reviews about Primitives in ~3 weeks. So if you would be ready to lead a review, let me know in this thread, and I'll give you more information.
The next review is going to be about Arrays.

I hope you'll be able to use your new knowledge and again, I would love to get suggestions. :-)

  [1]: http://www.codecademy.com/de/courses/javascript-beginner-en-ASGIv/0?curriculum_id=506324b3a7dffd00020bf661/#!/exercises/3
  [2]: http://www.codecademy.com/de/courses/javascript-beginner-en-ASGIv?curriculum_id=506324b3a7dffd00020bf661
  [3]: http://www.codecademy.com/de/courses/javascript-beginner-en-ASGIv/1/#!/exercises/1