This week we're going to touch a really complex and hard to understand topic. Don't worry about if you don't get it right away, we're going to take it slow and probably do this lesson over the next two weeks. Today we're going to begin by learning the binary number system. Yes, this isn't a programming review, yet, but it is essential to the programming concepts we're going to discuss.

The binary number system is a number system just like decimal (i.e. 0-9) except that it has its own notation that is easier to store in a computer. Instead of having 10 digits (0-9) like decimal, binary, meaning composed of two parts, has only two digits, 0 and 1. If any of you know circuits, binary somewhat represents high voltage versus low voltage (but not exactly). All the information stored on your computer is stored as binary. Crazy, right? Well, how do we count in binary or write numbers in binary? We're going to take this slow but hopefully by the end, you understand and love what I show you.

    0 => 0
    1 => 1
    2 => 10
    3 => 11
    4 => 100

Above, I've defined the first 5 numbers in binary that correspond to 0-4 in decimal. Now, you're looking at me and asking "how does 2 equal 10 in binary?" My response is with an image of one of my favorite shirts:
![alt text][1]

To really understand this, we're going to start by breaking down decimal into it's components. Take the number 192 for instance. Breaking it down into its exponential parts we find that

    (1 * 10**2) + (9 * 10**1) + (2 * 10**0) #this is written in Python so try it if you don't believe me
    => 192

I bet you haven't thought of numbers like that before. Similarly, binary uses this multiplication-addition method which is used to define any base, called a [radix][2]. So to represent 192 in binary, it would be

    0b11000000 #this is how you write binary numbers in Python
    (1 * 2**7) + (1 * 2**6) + (0 * 2**5) + (0 * 2**4) + (0 * 2**3) + (0 * 2**2) + (0 * 2**1) + (0 * 2**1)
    => 192

Do you see how that works? Pretty neat, right? So, now we're going to look at how you convert from binary to decimal and vice versa. Well, I lied a little bit. We've already seen the binary to decimal approach as shown above. You just need to multiple the value out. But what about the other way? The best way to convert decimal to binary is using division and modulus division. I'm going to demonstrate changing 192 to binary and then explain what everything means.

    192 => 96 r0 => 48 r0 => 24 r0 => 12 r0 => 6 r0 => 3 r0 => 1 r1 => 0 r1

What I have done is written what a division by 2 does at each step. 192/2 = 96 and 192%2 = 0, or 96 r0. You keep doing integer division until you reach 0 (1/2 = 0 in integer division). Now, how do we build the binary string? It's simple, read the remainders right to left and write them left to right. So for the above example, we get `11000000` which indeed matches the value I showed you previous. Now, you're not going to want to always do this math so here's a short cut that does this for you in Python:

    bin(192)
    => '0b11000000'

Python returns a string with the binary representation of the value passed in to the function. It does a string because of the `b` designating we're in binary. Unfortunately, you can't do operations on this string so you'll have to convert it to an integer again to do any meaningful math. You can do the following to convert the value back to an integer:

    x = bin(192)
    int(x, 2) + 100
    => 292

The `int()` function takes in a value (usually a string) and an optional second argument which is the radix of the string you're trying to convert. So above, I'm telling Python to convert the binary string to an integer and that the string is in base 2. Later we'll learn about a few other base systems, specifically 8 and 16, that will make this second argument more prevalent.

This is a lot of information so I'm going to end our discussion here this week. Please ask questions if any of the above information confuses you. Next week, we'll explain binary operations and their higher purpose in programming. Enjoy.


  [1]: http://www.superiorsilkscreen.com/546-592-thickbox/there-are-only-10-kinds-of-people-those-who-understand-binary-and-those-who-don-t.jpg
  [2]: http://en.wikipedia.org/wiki/Radix