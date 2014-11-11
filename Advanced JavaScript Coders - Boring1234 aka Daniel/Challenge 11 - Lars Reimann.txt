**The background:**
This challenge is about the *Tower of Hanoi* puzzle. Somewhere in the center of the world there is a hidden monastery. The monks' only task is to move 64 golden discs in a very specific way to bring about the end of the world. They are stuck though and ask you for help. The monks promise to refrain from dooming the world if you can solve an even more general problem...

**Your task:**
You have three rods, let's call them A, B  and C. There are n discs on rod A ordered from largest to smallest. The largest one is at the bottom. Here is a "picture" of this, where n - the number of discs - is 4:

            |                   |                   |
            |                   |                   |
            |                   |                   |
          ----                  |                   |
        --------                |                   |
      ------------              |                   |
    ----------------            |                   |
            A                   B                   C


You now have to move all those discs to rod B. You may only move one disc at a time and no larger disc may rest on a smaller one. You can only move the top disc of each stack. It is possible to use rod C in any intermediate step.

**Milestones:**
a) Write a text-based solver for this. It is not required to do this using a minimal number of steps. You can denote moves by A -> B or something similar, since only the top disc can be moved. 
b) Now try to use as few steps as possible. 
c) Use the canvas element to create a graphical simulation. 
d) For added difficulty also try to make it animated or add buttons to go through it step by step.

**Tips:**

 - Try it yourself for 1, 2, 3, 4 or 5 discs. Instead of discs you can take books of different sizes. Maybe you see a pattern.
 - You can use [this][1] as a template for tasks c) and d).
 - If you are really stuck have a look at this [solution][2]. Do not look at the source code, though. ;) A quick note on notation: move(n, b, c, d) means that you move n discs from rod b to rod c using rod d for intermediate steps. So move(2, 0, 1, 2) says for example that you move 2 discs from rod 0 to rod 1. Rod 2 can also be used.

This is a _tough_ challenge, so feel free to post your result no matter how far you got. Good luck and have fun!


  [1]: https://gist.github.com/Ignavia/6156688
  [2]: http://www.codecademy.com/users/5053369561ce1a0002058c92/projects/500c7558d143430002002551