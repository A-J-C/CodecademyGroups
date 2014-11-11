Hey everyone,

Wanted to share my thoughts on what makes a good bug report, seeing as how you all are the next generation of future bug reporters and educators! 

When we report bugs to the developers, it typically follows this style so that the bug squasher of the week (we rotate) can take one glance and understand the problem and how she might reproduce it. 

## General Good Tips

 * **Writing clearly is essential.** If the engineer can't tell what you meant, you might as well not have reported it because they won't know what to do. Avoid generic statements like "Exercise not working." Focus instead on what specifically is broken, e.g. "No response when user clicks "submit"" 
 * **The more information the better.** Try to make very clear what happened and what is speculation of the cause.
 * **List what you did, in what order.** If you can do the same thing two different ways, state which one you used. Did you click "Next exercise" or did you press CMD+D?
 * **Be careful of pronouns.** Don't use words like "it", or references like "the window" when it's unclear what they mean. Use editor, console, forums and so on.


## Typical Structure
### Description of the bug happening

A one line sentence describing **what the bug is** and what **browser** it is happening in. 

*Example: Default code passing as correct in Firefox 19.0 for jQuery exercise in new user interface. Possibly related to SCT errors?*

### How to reproduce 

This is a numbered list of steps for how the developer can see the bug himself. 
 2. The first step is to visit a URL
 3. The next step is an action
 4. The final step is the result they should see, e.g., the bug. 

*Example:* 

 *1. Visit http://www.codecademy.com/courses/javascript-intermediate-en-txGOj/4/3 in Firefox*
 *2. Click "Submit" (don't modify code)*
 *3. See "That's correct!" message appear* 