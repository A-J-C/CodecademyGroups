Hello,
it's time for another review. :-)
Unfortunately this one is a little late, so I'm sorry for this.
**Today's topic:** Advanced Arrays
We've had a look at arrays last week, so this week we are going to dive deeper:
 1. Multidimensional Arrays
 2. Jagged Arrays
 3. Looping through Multidimensional Arrays
 4. Why to use Arrays

#### 1. Multidimensional Arrays
*Multidimensional what?* Well, Multidimensional Arrays. :-)
Last time we've learnt that arrays can hold different data types like booleans, strings and numbers. But what happens, *if an array contains an array*? Well, then we call this array a *multidimensional array*, as you can create tables (two dimensional) or cubes (three dimensional) or even things with more dimensions:

    var myMultidimensionalArray = [["Name","Age"],["Bart",10]];

This would be a *2x2 two-dimensional array*. The `2x2` means, that we have two rows and two columns, if we wrote it as a table:

    "Name" "Age"
    "Bart" 10

If we wanted to access the first value `"Name"`, we would have to use something like `myMultidimensionalArray[0][0]`, so you put the index of the second array right after the first one.
So let's try to create a *3x3x3 three-dimensional array* and let's print the value in the middle (Imagine a 3x3x3 cube and number the fields):

    var myNewArray = [[[1,2,3],[4,5,6],[7,8,9]],[[10,11,12],[13,14,15],[16,17,18]],[[19,20,21],[22,23,24],[25,26,27]]];
    console.log(myNewArray[1][1][1]);

This is quite confusing, isn't it? :-)
I've choosen numbers from `1` to `27` (instead of `1,2,3` again and again) to show you, how much information can be stored in a 3x3x3 array, so try to imagine, how big numbers in a 4x4x4x4 array could be, there would be even `256` numbers. ;-)
Extremely confusing and difficult, so now let's do something different, *Jagged Arrays* are something different, aren't they?

#### 2. Jagged Arrays
Actually *Jagged Arrays* are just multidimensional arrays, whose elements can be of different dimensions and sizes. So the following array is a jagged array (having two rows):

    var jagged = [[1,2,3],[4,5]];

Sometimes there may be cases jagged arrays are useful, but often you'll use conventional multidimensional arrays.

#### 3. Looping through Multidimensional Arrays
Just as we can loop through a normal array, we also can loop through a multidimensional array (here a *3x3 two-dimensional array*):

    var myArray = [[1,2,3],[1,2,3],[1,2,3]];
    var i,j;
    for(i=0;i<myArray.length;i++)
    {
    	for(j=0;j<myArray[i].length;j++)
    	{
    		console.log(myArray[i][j]);
    	}
    }

As you see, this is not easy, but you'll need this, if you deal with multidimensional arrays. Usually you loop through multidimensional arrays using a `for` loop, you *could* use a `while` loop, but it would be quite similar, and as we've had something similar before and as this is not very common, I won't show this in this review.
But I'll show you another example: Let's loop through the *3x3x3 three-dimensional array* called `myNewArray` from the example above:

    var myNewArray = [[[1,2,3],[4,5,6],[7,8,9]],[[10,11,12],[13,14,15],
    [16,17,18]],[[19,20,21],[22,23,24],[25,26,27]]];
    var i,j,k;
    for(i=0;i<myNewArray.length;i++)
    {
    	for(j=0;j<myNewArray[i].length;j++)
    	{
    		for(k=0;k<myNewArray[i][j].length;k++)
    		{
    			console.log(myNewArray[i][j][k]);
    		}
    	}
    }

I think you are able to see, what's important: You have to check `myNewArray.length`, then `myNewArray[i].length` and so on and you have to watch out, that you use the correct incrementors.
So this is an advanced, but useful technique. There is just one open question: Why shall I use (multidimensional) arrays?

#### 4. Why to use Arrays
Short answer: They are great to store data.
So you can store whatever you want to store in an array: Numbers (for example primes), strings (letters of strings are often stored in an array using the `split()` method), arrays (for example to store a board, for example for tic tac toe) and even objects.
The combination *arrays + objects* is great, as you can store lots of different data in an object and store these objects in an array, for example the Blackjack course here at CC uses these.
And at last, here is an example of a tic tac toe board (an example of a multidimensional array):

    var board = [[0,1,2],[0,1,2],[0,1,2]]; //3x3 Board; board[1][1] is the field in the middle

**Courses**
http://www.codecademy.com/de/courses/javascript-beginner-en-9Sgpi?curriculum_id=506324b3a7dffd00020bf661
http://www.codecademy.com/de/courses/working-with-indexed-associate-and-multi-dimensional-arrays?curriculum_id=4f4b35445cb288000300000c (not maintained anymore)

**Ending**
I hope you enjoyed this review. :-)
I would love to read suggestions. :-)
The next reviews will deal with the different data types in JS and will teach you basic knowledge about the Primitives in JS and you'll learn more about Booleans and comparisons. Then we'll move on to objects and with these we'll be able to understand arrays even better (for example you'll learn that arrays are objects, too, and you'll learn about associative arrays), so stay tuned. :-)
I hope this review helps and you've learnt a lot. :-)