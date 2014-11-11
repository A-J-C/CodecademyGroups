 - incrementing: the difference between `i++ and ++i and i-- and --i` 

These operators can be confusing to new coders because they make possible two separate operations in a single statement. 

Simple statements like these:
```
++i;  // This simple statement...
i++;  // is functionally the same as this one...
```
are actually functionally equivalent: they cause the variable `i` to be *increased* by one, in other words: `i = i + 1;`

The same is true for these two:
```
--i;  // This simple statement...
i--;  // is functionally the same as this one...
```
which both cause `i` to be *decreased* by one, as in `i = i - 1;`

The observant student might ask, *If they are the same, why do we need both of 'em?*

Good question! The answer is that they can be *included* in a *compound*  statement! 

Let's say `i` is 3, consider this:
```
console.log(++i); // What will be displayed???
```
What we have in `console.log(++i);` are actually two operations combined into one statement. When it is finished executing,  4 gets displayed, while `i` will become 4.

This compound statement can be broken into two operations like this:
```
i = i + 1;
console.log(i); 
```

This statement:
```
console.log(i--); 
```
equals these two operations:

```
console.log(i);
i = i - 1; 
```
So, assuming `i` is 3, 3 will be displayed, and `i` will become 2.

**Exercises:**

There are two more to consider. They are:
```
console.log(i++); 
```
```
console.log(--i); 
```
What two operations are combined in the compound statements above?

[Return To Master Menu](http://www.codecademy.com/groups/advanced-javascript-coders/discussions/53307af3631fe9e8de00103b#discussion-53307af3631fe9e8de00103b)