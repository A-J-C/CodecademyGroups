Hello,
this is the second review. :-)
There are still open reviews in two weeks, so if there is anyone leading some reviews about the Primitives, just let me know. ;-)
Back to this review:
**Today's topic:** Basic [Arrays][1]
You should have a basic understanding of Arrays, so this review should be a real *review*.
The structure of this review:
 1. Creating an Array
 2. Accessing values of an Array
 3. Heterogeneous and homogeneous Arrays
 4. Looping through an Array

#### 1. Creating an Array

     var myArray = [];

Hooray, we've created an array! (It rhymes! `:-)`)
But this array is an **empty array**. Usually you use arrays to store (lots of) data, so let's add some content:

    var myArray = [2,4,6,8,10];

Now our array `myArray` contains multiples of `2`, so we've stored some multiples of `2` in our array. But how can we access them?

#### 2. Accessing values of an Array

Well, arrays have **indices**. And these indices start at `0` and go on until `array.length-1`. So, if we want to print the third multiple of `2`, our code would be the following:

    var myArray = [2,4,6,8,10];
    console.log(myArray[2]);

And if we want to get the first one, we would have to use the following code

    var myArray = [2,4,6,8,10];
    console.log(myArray[0]);
And if we wanted to get the fifth element we could use this:

    var myArray = [2,4,6,8,10];
    console.log(myArray[4]);
You are familiar with this? Yes? Great! :-)
So let's remember the most important point: Indices of arrays start at `0`.

#### 3. Heterogeneous and homogeneous Arrays

Okay, so now let's move to a topic, which might be new for you. Lets cover Heterogeneous and homogeneous arrays. Well, actually it is quite easy:
Arrays can hold many different data types: Arrays can hold strings `"Hello!"`, numbers `6`, booleans `true`, and objects `{name: "boring12345"}` (and arrays, which are also objects; we'll cover this next week).
Okay, now we know, arrays can hold different data types, but what about heterogeneous and homogeneous arrays?
Well, a *heterogeneous array*, is an array, which contains different data types. An example:

    var hetArray = ["boring12345", 2234, true];
So a *homogeneous array* has to be an array, which contains one data type:

    var booArray = [true, false, true, true, false];
    var numArray = [2,4,6,8,10]; //Do you know this one? :-)
    var strArray = ["Yes", "No", "Maybe"];

Everything clear?
If yes, you've (probably) learned some new terms. :-)

So now we have our homogeneous array `myArray` from the part, what could we do, if we wanted to print the values?
Well, we could use five `console.log()`s, but this is conbinable with [D.R.Y.][2] (Another one: The "[Rule of three][3]"). So we have to loop through the array.

#### 4. Looping through an Array

Usually you use a `for` loop to loop through arrays. It could look like the following:

    var myArray = [2,4,6,8,10];
    var i;
    var length = myArray.length;
    for(i=0;i<length;i++)
    {
    	console.log(myArray[i]);
    }

This is quite advanced: We've declared the `length` outside the loop and assigned the value `myArray.length` to it. You can do this, as arrays have a `length` property, how this works will be explained in another review.
So the loop runs from `0` to `myArray.length-1` (Do you remember this? `:-)`) printing the values of `myArray` at `i`. This is quite useful, isn't it?
This wasn't the **Advanced JavaScript Coders** group, if there wouldn't be another example, which combines, what we've learned. So let's combine "Looping through an Array" with "While loops":

    var myArray = [2,4,6,8,10];
    var i = 0;
    var length = myArray.length;
    while(i<length)
    {
    	console.log(myArray[i]);
    	i++;
    }
I think you are able to understand it, although this is not very common, so use the `for` loop instead.

I think you now have a basic understanding of arrays, next week's review will deal with multidimensional and jagged arrays, so we're going to dive deeper.

**Courses**
http://www.codecademy.com/de/courses/javascript-beginner-en-NhsaT/2?curriculum_id=506324b3a7dffd00020bf661/#!/exercises/0

**Ending**
I hope you've learned something from this review. :-)
I would love to read suggestions and feedback and yes, the next one will dive deeper. ;-)
Again, if there is anyone, who is ready to lead some reviews about the Primitives, he/she can tell me in this thread.

I hope the review helps. :-)



  [1]: http://en.wikipedia.org/wiki/Array_data_structure
  [2]: http://en.wikipedia.org/wiki/Don%27t_repeat_yourself
  [3]: http://en.wikipedia.org/wiki/Rule_of_three_%28computer_programming%29