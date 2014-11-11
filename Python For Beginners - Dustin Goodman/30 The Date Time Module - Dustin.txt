Have you ever found yourself needing to use dates, times or a combination of the two for a project you were working on? Did you need a format that was compatible with a SQL database or API? Luckily, Python is shipped with such a package called `datetime`. Let’s explore the package and you can read more details at the [official document](http://docs.python.org/2/library/datetime.html).

**Constants**
The `datetime` library ships with two basic constants `MINYEAR` and `MAXYEAR` which are the smallest and largest allowable years, respectively. You can import and use these constants as follows:

    import datetime
    print datetime.MINYEAR
    print datetime.MAXYEAR

**Available Types**
`datetime` supports five basic object classes: `date`, `time`, `datetime`, `timedelta`, and `tzinfo`. 
We’ll look at each of these over the next few weeks so we get a good feel for the library. Today, we’ll look at `date`.

**The date Class**
This class provides a date based off the Gregorian calendar. This class has both class functions and instance methods for interacting with it. Let’s begin by looking at the class functions:

`datetime.date(year, month, day)`
- This is the initializer/constructor for making your own date object.
- It’s 3 arguments are mandatory and must appear in the order shown above.

`datetime.date.today()`
- This class function creates a new `date` object that is set to today’s date.

This class also has some built in attributes. They are:

`datetime.date.min` 
 - the earliest representable date or January 1, 1

`datetime.date.max` 
 - the latest representable date or December, 31, 9999

`datetime.date.resolution`
 - the smallest possible difference between non-equal objects or 1 day

Now, let’s look at a `date` instance. These have some attributes and several methods. We’ll only look at a few of these methods that I think are the “most” useful. Each `date` object has three attributes/instance variables. They are `year`, `month` and `day` and are all integers. Now, let’s look at the methods:

`date.replace([year],[month],[day])`
 - This method takes your date object and returns a “new” date object with whichever field you choose to change. This means you’ll have to assign the return of this function to a new variable. If you don’t want to specify all three arguments for `replace`, you can simply call it like `d.replace(day=15)` if you wanted to change a single value.

`date.weekday()`
 - This method returns an integer representing what day of the week the date object represents where 0 is Monday and 6 is Sunday.

`date.isoformat()`
 - This method returns a string with the date formatted as `”YYYY-MM-DD”`.

`date.strftime(format)`
- This method returns a string with the date formatted to your specification but restricted to specific string formatters, i.e. `%m` is month, `%d` is day, and `%y` is year.

Now that the library is defined, let’s show an example for you to run through on your own.

    import datetime
    x = datetime.date(1990,11,02) #date(year, month, day)
    y = datetime.date.today()
    a,b = datetime.date.min, datetime.date.max
    if x > a and x < b:
         print “%s is a valid date” % (x.isoformat())
    x =  x.replace(year=2013)
    print “x is now %s” % x.strftime(“%m/%d/%y”)
    print “and is the %dth day of the week” % x.weekday()

That’s it for this week. See you next week with a new part of the `datetime` library.