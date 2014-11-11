In this final installment of the `datetime` module, we’ll be reviewing the `tzinfo` class. `tzinfo` is an abstract class. This means you should really never call it directly. `tzinfo` is the representation of the timezone corresponding to the `datetime`, `date` or `time` object. So, if you wanted to use `tzinfo` and pass it into the constructor of one of the other classes, you would have to define class that **inherits** from `tzinfo`. For this to work, you’ll have to create and define the following methods for your new class depending on what object you are using: `utcoffset`, `dst`, `tzname`. There is also an optional method that you can override if you so choose: `fromutc()`. Let’s delve into these methods and then create a concrete example that shows how to use the class.

`utcoffset(self, dt)`
- This method should return the local time offset from UTC. The `dt` parameter indicates whether or not we’re in daylight savings. So, if we were on the east coast of the United States not in daylight savings, this function should return `-300` minutes. If we were east of UTC, this number would be positive.

`dst(self, dt)`
- This method should return the time adjusted for daylights savings. If daylights savings information is unknown, the method should return `None`. The `timedelta` class comes in great use in this method.

`tzname(self, dt)`
- This method should return the timezone’s name corresponding to the ojbect. From our previous example, this could return `”EST”`, `”-500”`, `”-5:00”`, `”US/Eastern”`, etc. 

`fromutc(self, dt)`
- This method is optional but if you choose to implement it, it should return the current time in terms of UTC.

Below is a short example that demonstrates how you would write a concrete class that derives from `tzinfo`.

    class UTC(tzinfo):
        def utcoffset(self, dt):
            return timedelta(0)

        def tzname(self, dt):
            return “UTC”

        def dst(self, dt):
            return timedelta(0)

Now with your new skills, you should be able to create any datetime object of your dream that works with your database configuration or some program you want to make. Hope you enjoyed this 5 part lesson on the `datetime` module.
