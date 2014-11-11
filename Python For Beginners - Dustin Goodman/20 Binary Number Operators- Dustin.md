Last week, we learned what the binary number system was, how to count in it, and how to convert to and from decimal with binary. That's nice but we need the practical application of binary. This week we're going to discuss the operators we can use for binary numbers and their application.

In Python, we have 3 binary operators (take two arguments) and 1 unary operator (takes one argument) that work on binary numbers. These operators are "and", "or", "exclusive or" and "not". "Wait! That sounds really familiar." That's right, we have 3 of those operators for our boolean statements already. In Python, we use the keywords `and`, `or`, and `not` to carry out these boolean operators when doing logical compares. To do comparisons of binary numbers, we use `&`, `|`, `^` and `~` which stand for and, or, exclusive or (xor), and not, respectively. Let's grow through an explanation of how each one works.

`&` is a bitwise comparison and which means it goes through all the data (which is in binary) and compares each bit. If they are both 1, then it returns a 1 in that place. If either of the bits is 0, it returns a 0 in that place. Here's an example:

    0b0011 & 0b0101 #3 & 5
    => 0b0001 #1

Similarly, `|` is also a bitwise comparison. However, it returns a 1 for any position that has a 1 in either value. Here's an example of this:

    0b0011 | 0b0101 #3 | 5
    => 0b0111 #7

The `^` operator is similar to the `|` operator, but it returns 0 if both values are 1, i.e.

    0b0011 ^ 0b0101 #3 ^ 5
    => 0b0110 #6

Finally, the `~` operator takes the complement (or inverse) of the operand. For example,

    ~0b0011 #3
    => 0b1100 #-4

These are all the bitwise operations. There are actually two more operators I failed to mention earlier. They are the left and right shifts whose operators are `<<` and `>>`, respectively. What this does is shifts in zeros in either the rightmost or leftmost position and removes the same number of bits (single digit of a binary) from the opposite side. Here are two examples:

    #left shift
    0b0001 << 2 #1 << 2
    => 0b0100 #4

    #right shift
    0b1000 >> 1 #8 >> 1
    => 0b0100 #4

Let's make some observations about the above operators. The `&` and `|` operators let us create special binaries called bitmasks. Anything `&` 0 is always zero and anything `&` 1 is always itself. Similarly anything `|` 0 is itself and anything `|` 1 is 1. Hence, we can test specific bits for specific values. Cool, right? The `^` lets us invert certain bits because anything `^` 1 is its complement, i.e. 0 -> 1 and 1 -> 0. Finally, the shifters work as multiplication (shift left) and division (shift right) by powers of 2.

This is a lot of information to absorb so again, please ask questions. The problem of the week this week is going to make you try a real world use cause of these bitwise operands. Have fun and see you next week!