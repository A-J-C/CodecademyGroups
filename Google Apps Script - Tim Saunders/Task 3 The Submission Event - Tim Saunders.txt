So hopefully, you’ve [set up a form][1] and used it to [trigger an email][2]. But that email wasn't that good was it? What we really want is to be able to customise the text in the message based on what the user has actually said. This is just a quick post (and sadly there are less pretty pictures) so let’s get to it.

    function OnSubmit(e) {
        MailApp.sendEmail("you@example.com","Your form was submitted!",
            "Oh hey there!" + 
            "\n\nSomeone called " + e.values[1] + 
            " submitted your form. They said that " + e.values[2] +
            " is their favourite colour because " + e.values[3] + "." +
            "\n\nLove from FormBot")
    }

(1) The trigger that we set up in the last task is listening for a [submission event][3] and when one comes along, it kicks off the function. What we want to do is pass the event in to the function as an argument. Note that there's nothing special about where started a new line in this code except trying to make it fit in the box!

 (2) You can see my function `OnSubmit(e)` has the event e as an argument. The form submission event is contains an array of all the values submitted by the form user, accessible via e.values. Arrays, hey? [We know about arrays][4]! No worries there. Remember that JavaScript is zero-based so to find the third item in that array, we want to use `e.values[2]`. It’s also important to note that in this situation the timestamp (the second the form was submitted) is always the first item in this array – so the first field you actually set up is at `e.values[1]`.

 (3) We've concatenated a couple of strings and variables to make a sentence which is pretty handy for writing an email. 

 (4) `\n` indicates a New line in JavaScript, useful for returning strings on multiple lines which can makes things easier to understand. 

 (5) Next, I added a name question to my previous form. If you add a question to a form, no matter where, it will appear as the last field on the spreadsheet of your results. You can drag this column but you’ll see a warning and your mileage may vary – if at all possible, things tend to work much more smoothly if you set your questions up in the right order to start off with.

 (6) Finally, if you've changed the name of your function, check that the trigger is still set up for your new function as in Task 2.

Now, go submit your form and wait for the magic email to pop up.

  [1]: http://www.codecademy.com/groups/google-apps-script/discussions/5101aa8eba7b3a74070007ff
  [2]: http://www.codecademy.com/groups/google-apps-script/discussions/5101d9262ec5a88b5400052b
  [3]: https://developers.google.com/apps-script/understanding_events
  [4]: http://www.codecademy.com/courses/javascript-beginner-en-9Sgpi?curriculum_id=506324b3a7dffd00020bf661