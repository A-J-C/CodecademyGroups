We've seen that submitting a Google Form creates an event with an associated array of values corresponding to an ordered list of the user's responses. If you're anything like me and find it easier to work with named variables rather than numbers, creating your own object might help. 

This way you will be able to reference the values without constantly having to count which question they are taken from - which can be especially confusing as we learnt in the previous tutorial that JavaScript is zero-based. 

    function OnSubmit(e) {
    
      var  NewSubmission = {  
        "Timestamp" : e.values[0],
        "Name" : e.values[1],
        "Favourite Colour" : e.values[2],
        "Explanation" : e.values[3],
      }
     
      MailApp.sendEmail("you@example.com", "Form submitted!",
                      "Oh hey there!" + 
                      "\n\nSomeone called " + NewSubmission["Name"] + 
                      " submitted your form. They said that " + 
                      NewSubmission["Favourite Colour"] +
                      " is their favourite colour because "  +
                      NewSubmission["Explanation"]] + "." +
                      "\n\nLove from FormBot")
    }

(1) I know - *I know* - you know how to create a new object and populate it with key value pairs using literal notation. But just in case it's been a while since you met a JavaScript object, [this lesson][1] has got you covered.

(2) What's that? You've already thought of a better way of setting this up? Of course you have. OK, now let's build in what we know about for..in loops, arrays and objects. **Create an empty object**.

    var NewSubmission = {};

(3) Right, next, **set up an array** of the property names for our object in the right order.

    var Properties = ["Timestamp","Name","Favourite Colour","Explanation"];

(4) Sweet. Now we're going to loop through the two arrays we've got, using the properties array as our object's keys and the event values array as the values.

    for(var i in Properties){
         NewSubmission[Properties[i]] = e.values[i];
    }

Here we've accessed the properties of the object using [Bracket Notation][2] (which can give us a bit more flexibility) inside of a [for...in loop][3]. Doesn't that look better? Doesn't save us much time or lines of code here but when you're working with more variables, you'll be glad you learned neat code like this.

Put it all together and you get;

    function OnSubmit(e) {
    
      var  NewSubmission = {}
      
      var Properties = ["Timestamp","Name","Favourite Colour","Explanation"];
      
      for(var i in Properties){
        NewSubmission[Properties[i]] = e.values[i];
      }
     
      MailApp.sendEmail("gassnippets@gmail.com", "Form submitted!",
                      "Oh hey there!" + 
                      "\n\nSomeone called " + NewSubmission["Name"] + 
                      " submitted your form. They said that " + 
                      NewSubmission["Favourite Colour"] +
                      " is their favourite colour because "  +
                      NewSubmission["Explanation"]] + "." +
                      "\n\nLove from FormBot")
    }

Now go try it out and let me know how it goes in the comments!

  [1]: http://www.codecademy.com/courses/spencer-sandbox/1?curriculum_id=506324b3a7dffd00020bf661#!/exercises/1
  [2]: http://www.codecademy.com/courses/spencer-sandbox/1?curriculum_id=506324b3a7dffd00020bf661#!/exercises/3
  [3]: https://developer.mozilla.org/en-US/docs/JavaScript/Reference/Statements/for...in