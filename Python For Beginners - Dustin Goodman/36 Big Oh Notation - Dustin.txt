Over the last few weeks, I've been giving you all sorting algorithms for the problems of the week. 
I wanted to start discussing these specific algorithms and their related data structures, but I thought it was important to expand your toolkits once again. If you don’t know what an algorithm or data structure is, then please go back and read [Dek’s review on Data Structures and Algorithms](http://www.codecademy.com/groups/python-fro-beginners/discussions/513db1703a03bbfc0b0006f2) before continuing. If you know this material, then let’s begin.

In Computer Science, programmers like to analyze their algorithms for efficiency. There are two types of efficiency they check: space and time. Computers are blazingly fast and can do small problems very quickly no matter the quality of the algorithm. However, as the problem size gets larger and larger, the programs take more and more time to run. Sometimes, your program can be written so poorly that it will take several days or even years to run on a relatively large set of data. This is where analysis becomes important. Programmers need a tool that helps them analyze the runtime of their algorithms. Here’s the catch 22: in most cases, you’ll have to give up memory for speed and vice versa. Luckily, memory is becoming insanely cheap and time is becoming more expensive so the focus has shifted towards time complexity rather than space complexity. How do we analyze the time though? You might be thinking to yourself that your computer is so fast that it won’t matter but trust me, my machine is a monster and I’ve managed to write bad programs that take several hours to run. This is where Big O notation comes into play.

Big O is a mathematical notation for describing the limiting behavior of a function when the argument tends towards a particular value or infinity. That’s means that you test a function to see how it reacts against any given input no matter how big or small it is. So how do we analyze code to do this? We count the number of instructions run. Let’s look at the following statement.

```python
if True:
  print “Hello, World!”
```

There are two instructions in this program. Each instruction counts for a constant no matter what the input is. This is an argument independent program and Big O. Hence, it is run in constant time or `O(1)` (read “Big Oh of Constant Time”). Now the real Big O is `O(2)` but we reduce our function down to the simplest terms without constants. Let’s look an example to make this clearer.

```python
x = []
for i in range(10):
  print “Added ”, i+1
  x.append(i+1)
```

This program has a loop so things get slightly more complicated. We have one instruction that gets run once and “2” instructions (I’m calling a single line an instruction no matter how complicated it actually is for simplicity sake) that are run as many times as the loop runs. Because the loop can be changed to an arbitrary number, let’s say the loop runs `n` times. Hence, the Big O for this program is `O(2n+1)` which we write as simply `O(n)` which reads as “Big Oh of Linear Time”. As you can see, we remove all the constants from the expression and leave it in terms of the largest factor. So an expression like `O(x**2 + x)` would reduce down to `O(x**2)` because `x**2` is the dominating factor. As functions get larger, we start breaking them down to their smallest unit then start chaining Big Ohs. 

Now that we have the tool, we will start analyzing algorithms and presenting in more detail over the next few weeks. Hope you enjoyed! 