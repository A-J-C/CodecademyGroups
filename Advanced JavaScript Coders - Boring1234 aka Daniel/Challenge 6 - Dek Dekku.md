Hi!

Here's a new challenge for you. We need a way to identify words that can be used to tag web pages by examining their HTML source.

Start by creating a function that accepts a string of HTML code, remove all the HTML tags (anything that looks like `<something>`), split the remaining text into words and return a list containing those words. Example:

    var html = "<p>a paragraph with <i>italic text</i> in it</p>"
    generateTags (html)
    
        => [ 'a', 'paragraph', 'with', 'italic', 'text', 'in', 'it' ]

Once you get this working, try and add more features to your function to make it more performing, elegant and/or useful like:

 * removing duplicates;
 * ordering the result (by frequency or A-Z)
 * handling up/lower case;
 * handling punctuation;
 * handling ISO Entities;
 * accepting a maxNumber of words to return;
 * accepting a minLength for the returned words;
 * accepting a minFrequency for the returned words;
 * removing words from a blackList;
 * use it in a web page;
 * and so on...

I've posted a comprehensive requirement list on Github:

https://github.com/nofatclips/generateTags

Questions?

(Edited to list the additional requirements. Refer to the external link for more details.)