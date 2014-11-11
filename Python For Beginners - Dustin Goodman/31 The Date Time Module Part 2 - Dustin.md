So last week we investigated the `datetime` package’s `date` module. Let’s continue today by exploring `time`.

The `time` object is very similar to the `date` object in several regards but has a few added features to better represent time. Unlike the `date` object, `time` has only one class method which is the constructor. Unfortunately, the `time` constructor is really ugly and has bad defaults. The constructor is:

    datetime.time([hour[, minute[, second[, microsecond[, tzinfo]]]]])

That’s right, every argument is optional. Unfortunately, they all default to 0 or `None`. Just for clarification, `microsecond` is the number of microseconds that have passed in the second if you really need that accuracy, and `tzinfo` is the time zone for the time being represented. This will come from the `tzinfo` module which we’ll discuss later in part 5.

The `time` class comes with three attributes: `min`, `max` and `resolution`. `min` is the earliest representable time which is 0 hour, 0 minute, 0 second and 0 microsecond. `max` is the latest representable time which is 23 hours, 59 minutes, 59 seconds and 999999 microseconds. `resolution` returns the smallest difference between two times which is 1 microsecond. 

Each `time` object has 5 read-only attributes. They are `hour`, `minute`, `second`, `microsecond`, and `tzinfo`. Seems kind of boring but we can live with this because it’s what we need. Finally, let’s look at the instance methods.

`time.replace([hour[, minute[, second[, microsecond[, tzinfo]]]]])`
- This method takes your time object and returns a “new” time object with whichever field(s) you choose to change. This means you’ll have to assign the return of this function to a new variable. If you don’t want to specify all three arguments for `replace`, you can simply call it like `t.replace(minute=15)` if you wanted to change a single value.

`time.time.utcoffset()`
- This method returns `None` if `tzinfo` isn’t set. Otherwise, it will return the minutes off from the time zone disregarding daylight savings.

`time.dst()`
- This method returns `None` if `tzinfo` isn’t set. Otherwise, it will return the minutes off from the time zone accounting for daylight savings.

`time.isoformat()`
- This method returns time formatted as `HH:MM:SS.mmmmmm+HH:MM` where the `mmmmmm` and `+HH:MM` correspond to microseconds and the UTC offset, respectively. If either value is it’s default (0 or `None`), then its component is omitted.

`time.strftime(format)`
- This works identically to the `date.strftime(format)` method, but you use `HH`, `MM`, and `SS` instead of the `date` specific formatters.

That’s it for this week. Stayed tuned next week for Part 3.