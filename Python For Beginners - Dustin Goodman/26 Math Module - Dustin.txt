This week is the beginning of a series of reviews we’ll be doing based on modules. We’re going to explore popular and useful modules and explore their power and tools. This week we’ll begin with the math module which is one of the most widely used modules.

The [Python math library][1] is huge and comprehensive. For this reason, we’ll be looking at a handful of the functions but if you want more information about a particular function, feel free to ask. To manage this library, we’ll tackle it in an organized fashion. First, we’ll look at constants. The math library has two extremely useful constants defined: `pi` and `e`. These constants are defined to as much precision as your computer can handle. So, let’s say you wanted to calculate the circumference of a circle, you could do the following:

    from math import pi
    def circum(rad):
        return 2*pi*rad

    print circum(4)
    => 25.132741228718345

You can import `e` in a similar fashion and use it in its relevant equations. Next, let’s look at some of the number theory and numeric representational functions.

These functions are made to complement commonly used functions in the Python library. These functions are used for the floating point versions of their standard library functions with the exception of `factorial`. These functions include `ceil`, `fabs`, `factorial`, `floor`, `isinf`, `isnan`. Some are self explanatory but let’s take a quick at them.

    import math
    math.ceil(4.44) #returns the nearest integer w/ 0 floating point rounding up
    => 5.0
    math.fabs(-4.213) #returns the absolute value of a number
    => 4.213
    math.factorial(4) #returns the factorial of the passed in parameter
    => 24
    math.floor(4.78) #returns the nearest integer w/ 0 floating point rounding down
    => 4.0
    math.isinf(1/1000000) #returns whether a floating point number is infinity or not
    => False
    math.isnan(1.1232) #returns whether a floating point number is not a number
    => False

Next, let’s focus on the power and logarithmic functions. The math library has a power and square root function but these are easily performed using the standard library exponent function `**`. Hence, let’s look at `exp` and `log`. `exp` takes a single argument and performs `e**n` where `n` is the argument. `log` takes one mandatory and one optional argument. The mandatory argument is the argument for the `log` function, i.e. log(30). The second optional argument is the base for the `log`. It defaults to natural log, `e`, but can be changed to any base of your choosing. Definitely think about using Python instead of a calculator in the future. ;)

The math library also contains all your essential trigonometric functions. It contains `cos`, `sin`, and `tan` along with their inverses `acos`, `asin` and `atan`. It also has a `hypot` function that calculates the hypotenuse of a triangle given the length of the `x` and `y` components.

The last two functions we’ll look at are the angle functions. The `degrees` function converts a number from radians to degrees. Similarly, the `radians` function converts from degrees to radians.

If you have any more specific questions about these functions or any other functions in the math library, please ask. That’s it for this week. Enjoy! :)

  [1]: http://docs.python.org/2/library/math.html
