We've got submitted data, we can roll it in to an object, we can send emails. It's time to add a little flash. We're going to tabulate that data we received so it's easier to understand.

(1) Let's build this from the ground up. First thing to consider is the fact that **the whole table will be a text string** which we will store in a variable called 'table'. Each time we add something to this table, we are are adding to this variable. It's just **string concatenation and assignment** (which we've done) within a loop (which we are of course experts on). We're assuming that NewSubmission is an object containing key:value pairs of our form data.

var table = "This is the first thing. ";
table += "This is the second thing. ";
// "This is the first thing. This is the second thing. "

(2) Say we wanted to **list all of our object's properties** on a separate line  - that's easy right?

    var table = "";
    
    for(var property in NewSubmission){
       table += property + "\n";
    }

(3) Now let's **add in the values** as well.

    var table = "";
            
    for(var property in NewSubmission){
         table += property + " : " + NewSubmission[property] + "\n";
    }

     
(4) OK, **now set it up in HTML**. First off we want to start and end our table with the right tags.

    var table = "<table><thead><tr><th colspan=\"2\" >This is the title!</th></tr></thead><tbody>";
    table += "</tbody></table>"

(5) Next, let's borrow that loop and **add in HTML tags**

    var table = "<table><thead><tr><th colspan=\"2\" >This is the title!</th></tr></thead><tbody>";
    for(var property in NewSubmission){
        table += "<tr><td>" property + "</td><td>" + NewSubmission[property] + "</td><tr>";
    }
    table += "</tbody></table>"

(6) Finally, time for a tiny **touch of style**

    var table = "<table style=\"border:2px solid black;width:500\"><thead><tr><th colspan=\"2\" >This is the title!</th></tr></thead><tbody>";
    for(var property in NewSubmission){
        table += "<tr><td>" property + "</td><td>" + NewSubmission[property] + "</td><tr>";
    }
    table += "</tbody></table>"

And there you have it. You can now use that variable table in the `htmlBody` of your `MailApp.sendEmail` and you'll see your data tabulated.

**Extra credit**
There's a couple of small things to add to this. When you've worked through the steps above and go your table in to your email, see if you can figure how to achieve the following;

(a) I want alternate rows to be coloured in
(b) I want to find a way to split my data and therefore my table in to different sections.

Let me know how you get on - I'll put my solution up shortly, but I wouldn't be surprised if someone has a neater one!