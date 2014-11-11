First off, I must apologize for such a late review. It has been a very hectic week for me, and I haven’t been able to organize anyone to cover for me either. That being said, we’re going to move reviews to Wednesdays to accommodate the offset from this week. Let’s begin...

So far we’ve covered the most practical components of the `datetime` module: `date`, `time`, and `datetime`. This week we’re going to cover `timedelta`. Whereas the other three objects represent set times or dates, `timedelta` represents the elapsed time among objects. It has a very simple, yet long, constructor.

    timedelta([days[, seconds[, microseconds[, milliseconds[, minutes[, hours[, weeks]]]]]]])

As you can see, all the parameters are optional. If you choose not to set any, all the values default to 0. The object only stores milliseconds, seconds, and days internally and calculates values like minutes, hours, weeks, etc. based on the preexisting data.

The `timedelta` object has three class attributes: `min`, `max`, and `resolution`. `min` produces a `timedelta` object set to -999999999 days. `max` produces a `timedelta` object set to 999999999 days, 23 hours, 59 minutes, 59 seconds and 999999 microseconds. `resolution` produce a `timedelta` object set to the smallest difference between two time objects, i.e. 1 microsecond.

A `timedelta` object has a single instance method which is `total_seconds()` which returns the total number of seconds contained in a `timedelta` object.

The `timedelta` object is a very simple object that can be used with `date`, `time` and `datetime` to determine differences in times and help with simple date calculations.

That’s it for this week. Next week we’ll conclude our discussion about the `datetime` module. Have a good week and happy coding!
