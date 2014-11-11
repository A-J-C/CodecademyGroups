@boring12345, if you object to this, kindly say so, please. Thanks.

Building upon hkapur97's Challenge 1, how about we build a function (or set of functions) that takes a parameter `n` and finds the `nth` Prime Pair?

Prime Pairs, we will recall, are sets of prime numbers that are separated by only one number, the even number between them. (5,7) is the first prime pair, (n=1). (11,13) corresponds to (n=2); (17,19) to (n=3).

Here is where it starts to get dicey. Using a brute force approach,

    [p0, p1] = [ n*6-1, n*6+1 ] for 0 < n < 1700
    
there is not always a corresponding prime pair for every value of `n`. n=4 will not return a pair, but n=5 will (29,31). n=6 does not, but n=7 does (41,43).

If we start with the brute force, and use it to evaluate for any `m`, then we at least a have a checker. Next we need to iterate up `m` to arrive at the next actual pair, which we can now assign to `n`. n=4 should return (29,31) and n=5 should return (41,43).

This is a huge challenge, so it might be best if we collaborate a little on it, rather than attempting to outdo one another. The finished code will be the outcome, and we can all have a part in it.

Who wishes to start us out?