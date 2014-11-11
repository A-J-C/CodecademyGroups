You might have noticed that the [date](http://www.codecademy.com/groups/python-fro-beginners/discussions/51dae0ab7c82ca812204d793) class doesn't have properties for hours, minutes and seconds. And the [time](http://www.codecademy.com/groups/python-fro-beginners/discussions/51e44a87631fe9442d006521) class doesn't have properties for year, month and day.

This is great: concerns are nicely separated, each class does exactly what it needs to do, no more no less, I don't have to create objects more comples than I actually need and so on. But what if I need to represent, say, the time and date of an event, years to milliseconds?

If I want to represent the exact moment of my birth, I need to store both the date and the time. Do I need to use two separate objects for this? If I want to know how many seconds passed from my birth up until now, do I need four objects? Do I need to write all the code to do that?

Fear not, since the [datetime module](http://docs.python.org/2/library/datetime.html) has a [datetime class](http://docs.python.org/2/library/datetime.html#datetime-objects) to do this and more. Yes, the class has the same name as the module. Don't confuse them!

To create a `datetime` object you have several options. You can use the contructor:

    my_birthdate = datetime(year, month, day[, hour[, minute[, second[, microsecond[, tzinfo]]]]])

It takes many arguments, but only `year`, `month` and `day` are mandatory. Since `datetime` is a `date` composed with a `time` object, the meaning is exactly the same you saw the past weeks.

You can also build an object from a [UNIX timestamp](http://en.wikipedia.org/wiki/Unix_time) (number of seconds since 1/1/1970) using:

    my_birthdate = datetime.fromtimestamp(timestamp[, tz])

As usual, the timezone is optional.
You can use an "ordinal", that is the number of days since day one of year one:

    my_birthdate = datetime.fromordinal(ordinal)

For example, today is:

    >>> from datetime import datetime
    >>> datetime.now().toordinal()
    735072
    
As you might have guessed, `datetime.now()` creates an object representing the date and time of the exact moment when the method gets called, and `toordinal()` converts it to ordinal. Note that this way you are actually only representing the date, not the time.

If you have a formatted string representing date and time, you can create an object using:

    my_birthdate = datetime.strptime(date_string, format_string)
    
where you have to pass both the date and time string, and the format string, which is the same you would pass to the `strftime` you saw in the [date review](http://www.codecademy.com/groups/python-fro-beginners/discussions/51dae0ab7c82ca812204d793).

Last but not least, if you already have a `date` and a `time` object and just want to stick them together, then use the `combine` method:

    my_birthdate = datetime.combine(date, time)
    
This variety of factory and constructor methods allows you a great degree of freedom and flexibility in the development of your application. You can represent dates and times using whatever convention suits you best: Python has a method for that!

Next time we'll see what we can do with these objects once created, but since I'd hate to leave you with a dry mouth, I'll guide you through a simple example in the [problem of the week](http://www.codecademy.com/groups/python-fro-beginners/discussions/51ee80837c82ca937400670c).
