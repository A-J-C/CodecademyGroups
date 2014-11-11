## Prior Requirements 

 - [Web Fundamentals Track][web-fundamentals-track]

## Introduction 
I would like to start with pointing out that I'm a newbie in the Web Development world and thus as every passionate self-study student I desire to find some good, and the most important  - comprehensive, guidelines. Due to the huge amount of information on the Web, sometimes it can be really hard to filter all the resources. But for those who are here I think it is exactly the right place to find what you  need.

In this guide I want to cover the following:

- How do the CSS rules work together?
- What are CSS Cascade, Inheritance, and Selector specificity?
- What is the important declaration? 
- Tips on resolving conflicting rules

I really hope you'll read this article to the end, because these knowledges will give you a solid base on how to resolve the most common problems when applied styles don't work the way you want them to. OK, enough chatting, let's get started!:)

## Remembering CSS basics
CSS stands for "Cascading Style Sheets". It is the language used to describe how documents written in a markup language (such as HTML or XML) are supposed to look like.

A CSS document is composed by several rules (or "styles"). Each rule is composed by a selector(s) and/or pseudo-classes, followed by a declaration block that contains properties and values.

    selector [, selector2, ...] [:pseudo-class] {
        property: value;
        [property2: value2;
        ...]
    }

Here is an example of such a rule:

    body, p {
        font-size: 14px;
        color: navy;
    }

In this example, we have one rule composed by two selectors: `body` and `p`. Inside the block declaration we have two properties being affected: `font-size` with the value of *14px*, and `color` with the value of *navy*.

These are the basics of CSS that we learned in the [Web Fundamentals Track][web-fundamentals-track]. Still, for the sake of memory, here is the [Wikipedia article](http://en.wikipedia.org/wiki/Cascading_Style_Sheets) that sums up CSS. Also, in case you want to go beyond remembering CSS you can always check all our sources in the [ What do I need to learn how to build a website?](http://www.codecademy.com/groups/html-projects/discussions/51e69fe27c82ca29510040c3#) guide. 

## Add CSS to your HTML
For those of you who have forgotten there are two main ways to include a CSS code into your HTML code:

1. link an HTML file to a CSS file 
2. directly embed CSS code inside your HTML file

### Linking a CSS file to an HTML file

Here you need to link the .css file to .html document. This is done by using the HTML tag `<link />`, which is a self-closing tag, that must be placed inside the `<head>` tag of your HTML file:
              
        <head>      
            <meta charset="UTF-8" />
            <title>Web Page</title>
            <link rel="stylesheet" href="path/to/file.css" type="text/css" />
        </head>
        
Though, in *HTML5* **you can skip** the forward slashes `/` in self-closing tags, and also `type="text/css"` in `<link/>` tag, I really got used to type them anyway, just in case.        
If you have some issues with writing the path to your CSS files or images, or any other files from your local hard drive - in this [Stackoverflow discussion](http://stackoverflow.com/questions/3655059/html-pick-images-of-root-folder-from-sub-folder) you may find some good explanation.

For more information about the HTML `<link/>` tag (including the HTML5 version) you can refer to these detailed descriptions:

- [Mozilla Developer link reference](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/link)
- [sitepoint link reference](http://reference.sitepoint.com/html/link)

### Embed CSS code into HTML file
In this option you have to use the `<style> </style>` tag (which goes inside the `<head> </head>` tag) and place the CSS code inside it:

    <style type="text/css">
        h2 {color:#000;}
    </style> 

This second method is usually used when:

- You have a small CSS code for a demo and you do not want to bother yourself with the creating a new CSS file and linking it to the HTML using the first method;
- When you want to overwrite a style that has been previously applied by another CSS rule. 

Once again, you can find detailed information about the `<style> </style>` tag in the following links:

- [Mozilla Developer style reference](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/style)
- [sitepoint style reference](http://reference.sitepoint.com/html/style)

## Conflicting CSS rules
First of all let's define the term "conflicting rules". A conflicting rule arises every time you have multiple rules, assigning different values to one property belonging to the same selector. Following is an example of two conflicting rules:

    /* rule 1 */
    body, p{
        color: red;
    }

    /* rule 2 */
    p {
        color: blue;
    }

In this example, both rules apply a different value to the property `color` (*red* and *blue*) for one common selector, which is `p`. Which rule will win? What can we expect? This often results, in unexpected results.

Fortunately, there are three main CSS principles that define and manage which value for the property `color` will be used when the conflict happens: 
 
- Cascade; 
- Inheritance;
- Selector specificity.

Additionally, we also present two more ways to help you solve CSS conflicts between rules in the sections:

- Important Declaration (use with caution!);
- Tips on resolving styles conflicts.

### CSS Cascade
*Cascade* - is the sorting order that browsers and other applications use in order to known which rules to apply and in which order to do it. It is a complex system, but for now suffices to say that it handles the interaction of conflicting rules.

The CSS Cascade solving process has many rules, for now however we are interested only in two:

1. The last rule wins!
2. CSS rules are cumulative.

When it comes to conflicting rules, CSS Cascade deals with two main sets problems:

1. When you have the same property with different values targeting one selector from within different rules; 
2. When you have many rules with different properties again for one particular selector. 

To exemplify how CSS Cascade would solve the first problem, we have the following scenario:

- We have CSS rules in different locations;
- These rules all affect the same selector, which is `p`;
- They affect the same property `color`, with different values.
 
![The last rule wins!](https://raw.github.com/Ksenja/My_Tut/master/img01.png)
 
Here you can see the meaning of the word "cascade" - the browser applies the rules in the order that they are found, that is, down through the document. In other words - **the last rule is overwriting the previous ones** - thus, the paragraph will be purple.
Thereby the order in which you put your rules matters a lot.

For the second problem, we have the following scenario:

- We have CSS rules in different locations;
- These rules all affect the same selector, which is `p`;
- They affect the different properties: `font-family`, `color` and `background`.

![Cumulative CSS rules effect](https://raw.github.com/Ksenja/My_Tut/master/img02.png)

In this case, the rules are applied in a **cumulative** manner, - our `<p>` element gets all the styling applied to it.

#### Additional information
So, remembering what we have learned so far about CSS Cascade:

- if several CSS rules compete with different values for the same property affecting the same selector, the last CSS rule always wins;
- when CSS rules do not compete, they are cumulative.

Here we have seen only the tip of the iceberg. For more information feel free to dig into the following sources:

- [sitepoint - The Cascade](http://reference.sitepoint.com/css/cascade)
- [w3 - The cascade](http://www.w3.org/TR/CSS2/cascade.html#cascade)
- [CSS Cascade Presentation](http://www.maxdesign.com.au/articles/css-cascade/)

### CSS Inheritance
*Inheritance* - the ability of receiving styles from parents by their children. I assume you are familiar with the term DOM(Document Object Model): for example, since the `<body>` tag is the parent element to all the elements that are inside of it - the rules applied to the body will be applied to its children as well:

    body  {font-family:Arial;}
    |
    |----header        *Arial*
    |       |
    |       |----h1    *Arial*
    |
    |----section       *Arial*
    |       |
    |       |----h2    *Arial*
    |       |
    |       |----p     *Arial* 
    |
    |----footer        *Arial* 
    
Thus, it really saves your time, you do not have to specify properties for all descendant elements.

Like CSS cascade, CSS inheritance also has a lot of rules to deal with problems. Once again, we focus on the two most common problems and we see how inheritance works to solve them:

1. Applying different property values to the same selector;
2. Applying different properties on different selectors.

In the first case, conflicting rules are solved by giving child-element rules a greater level of priority. In other words, **child-element rules overwrite parent-element rules**.

![Children override parrents](https://raw.github.com/Ksenja/My_Tut/master/img03.png)

In the second case, the cumulative behavior comes into play once again. This is similar to what happens in CSS cascade as well, with a few differences that we will see next.

![Cumulative CSS Styling](https://raw.github.com/Ksenja/My_Tut/master/img04.png)

#### Attention and Pitfalls
By now you probably think that CSS inheritance uses the same rules that CSS cascade uses, but between a parent and its children. This however is not completely true: 

1. not every single property is inherited by the children;
2. inherited properties are dependent on browser settings;
3. some properties have to be specifically targeted in order to change.

The first scenario can be both good and bad, depending on the situation. For example, a situation where this behavior benefits you is if you apply a border property to the `<section>` parent element. If every child-element had this border you would probably be quite annoyed:

![Border around every child-element](https://raw.github.com/Ksenja/My_Tut/master/img05.png)

In the reality you will have the border **only** around the parent section.

In another situation however, this can be bad. If you have a parent element with the `background-image` property set, and if you want to repeat the value of that background in every child element in order to create a fractal (per example), then you are out of luck because that property is not inherited either. 

Every time you use a property and do not achieve an expected result, you must be careful and remember this CSS pitfall. Here is the [full list of properties](http://www.w3.org/TR/CSS21/propidx.html) and their inheritance status in general ("Inherited?" column).

Even though we have the list however, the second problem still arises. Some properties (marked with "yes" on the list) will not be inherited by all elements due to the **default styling of the user agent**(your browser) applied to them. You can notice it when you create a rule for `<body>` with a certain font-size - the heading elements will not inherit that, because it has default font-size styling applied to it. 

Last but not least, there is the third problem. A specific example are the `<a>` elements, which will not inherit the value for the **color** property: most often it has a default value of *blue* applied by your browser. So, you have to directly target those elements to change their default styling. I had no idea about that until my own experience with that. A place with information on how to deal with that can be found at [Sitepoint.com](http://reference.sitepoint.com/css/inheritvalue), I recommend you to read through it.

I also found a great web resource that gives the comparison table of the default styling for IE 7 - 9, Firefox 3.6.3, Webkit (r57042), and Opera 10.51 - http://www.iecss.com/. 

#### Additional information
If you are a little confused do not worry it is time for a recap:

- Children rules override parent rules;
- Parent's rules can be inherited by child-elements (but it does not work for all properties).


For more information on CSS inheritance, you are welcome to read the following sources:

- [sitepoint Inheritance](http://reference.sitepoint.com/css/inheritance)
- [Inheritance and Cascading Styles in CSS Explained](http://www.webdesignfromscratch.com/html-css/css-inheritance-cascade/)
- [How CSS Inheritance Works in Web Documents](http://webdesign.about.com/od/advancedcss/a/aa073007.htm)

#### Web Dev Tools
You may say: "OMG! How do I keep it all in mind!?" - The savior comes to you, called Web Inspector. If you have not yet heard of it, then this is the right time to meet your new friend, which in fact is very useful, and even a necessary Web debugging tool.
Depending on which browser you use, it can be a built-in feature or you may have to download it from official websites.
With the help of this tool you can easily find out which property is being applied and/or inherited for each element on the page. These tools also allow you to check the source code of most websites and they allow you to edit it on the go, presenting you with a live preview of the changes being made (if you are wondering, it does not affect your code files at all).

![Web Dev tool in action](https://raw.github.com/Ksenja/My_Tut/master/img07.png)

Each browser has its own web inspector tools, some browsers even have more then one. To find more information about web browsers and web inspector tools check out our [Google Docs Spreadsheet](https://docs.google.com/spreadsheet/ccc?key=0AuUP5lxiQ9AodHNtUXA2WFBVYTVvZXl1RWZ3OGZIQkE#gid=0)!

### CSS Selector Specificity
*Selector Specificity* - mechanism used to solve conflicts between selectors when the others fail. The specificity of selector is used to determine which selector has precedence. 

Selector specificity is calculated by the amount of points assigned to the style's selector — a tag selector, class selector, ID selector, and so on. Here is how the system works:

-  `tag`  = ***1 point***;
-  pseudo-element selector (e. g. `::first-letter`) = ***1 point***;
-  `Class` = ***10 points***;
-  pseudo-class selector (e. g. `:hover`) = ***10 points***;
-  `ID` = ***100 points***;
-  `inline style` = ***1,000 points***.

Counting selector specificity:

![Selector Specificity Table](https://raw.github.com/Ksenja/My_Tut/master/img06.png)

In CSS selector specificity there is only but one rule that you need to know:

- Greater Specificity Score = Greater Precedence

#### Additional Information
This chapter was so short that the only thing you really need to know is the one rule previously mentioned.

What we have presented so far however, is only but a simplified scheme. To know how the real calculation happens and to better understand selector specificity visit the following resources:

- [W3C spec](http://www.w3.org/TR/css3-selectors/#specificity).
- [More Specific = Greater Precedence](http://www.htmldog.com/guides/css/intermediate/specificity/)
- [CSS Specificity: Things You Should Know](http://coding.smashingmagazine.com/2007/07/27/css-specificity-things-you-should-know/)
- [Specifics on CSS Specificity](http://css-tricks.com/specifics-on-css-specificity/)

### Important Declaration 
 **100% CSS killing weapon!** - it does not care where you located your styles, and what is going on with them - it wins no matter what. It was originally created to easily allow developers to override the specificity rules, but it can be dangerous.
 
![The important declaration overrides any rules with any specificity](https://raw.github.com/Ksenja/My_Tut/master/img08.png)

The only thing that can override an important declaration is another more specific important declaration. 

This weapon should be avoided in most cases, only use it if you have a very strong reason. For more information on the important declaration feel free to visit:

- [!important CSS Declarations: How and When to Use Them](http://coding.smashingmagazine.com/2010/11/02/the-important-css-declaration-how-and-when-to-use-it/)
- [Everything You Need to Know About !important CSS Declarations](http://www.impressivewebs.com/everything-you-need-to-know-about-the-important-css-declaration/)
- [The importance of the !important CSS declaration](http://www.webcredible.co.uk/user-friendly-resources/web-dev/css-important.shtml)
- [CSS !important Declarations](http://techtalk.virendrachandak.com/css-important-declarations/)

### Tips on resolving styles conflicts
 
- Keep track of the specificity and inheritance;
- Try to maintain the specificity as low as possible, otherwise you will get unnecessary complex styling: the more specific rules you apply, the more power you will need to override them. In conclusion, do not the following:

         #mainContent #menu #wrapper p {
                     propertyName: someValue;
          } 

- If you see that there are rules with three or more selectors already then consider how to reduce the specificity of your rules. The previous example could be replaced with:

        p {
           propertyName: someValue;
        }

- Place the most basic general style rules on top within your css file - those rules will be inherited and thus it will save you time in fewer rules to write and easier style maintenance.

- Avoid using local styling or inline styles - they add unnecessary weight and complexity to your code, modifying and maintaining your styles will become a nightmare. 

For more information and tips on how to manage CSS, feel free to dive into the following links:

- [100 Exceedingly Useful CSS Tips and Tricks](http://sixrevisions.com/css/100-exceedingly-useful-css-tips-and-tricks/)
- [Managing CSS conflicts](http://stackoverflow.com/questions/1918891/managing-css-conflicts)

## 2-in-1 Quiz & Practice 

### Task 1
What rule wins here? Try not to type it in your HTML/CSS editor in order to check your browser's output, but just concentrate, take a look at specificity selector table and you will get the answer. 
 
![Calculate selector specificity](https://raw.github.com/Ksenja/My_Tut/master/img09.png)

[Answer](https://gist.github.com/Ksenja/94ee1af8489bb109a3e2)    

### Task 2 
You can copy/paste this code. You have to apply grey color text to the entire list; 1st, 3rd and 5th items must have beige background color - #F5F5DC; 2nd and 4th items - must have light-blue - #ADD8E6 - background. There are many ways to solve this, so do not get upset if my answer is not the same as yours. Try to perform the task efficiently.

    <div id="our_services">
        <ul>
            <li>Great working team</li>
            <li>Front-end development</li>
            <li>Back-end development</li>
            <li>JavaScript and Python App development</li>
            <li>Web design and graphic</li>
        </ul>
    </div>

[Answer](https://gist.github.com/Ksenja/801576e306da02ac2fc3)

### Task 3
Assume you have a really big website with some amount of different `<section>`'s, `<article>`'s, `<ul>`'s and so on. You have to style the news sections above, so that you target only those particular elements. You would have to spend some time on planning how to locate your styles and how to assign them in an efficient way: 

- the font-family of all your website - Garamond, with size of 20px and color #fff;
- links of your second news section must be black, and without underline;
- **every news section:** must be 400px wide; top and bottom margins - 0, left and right margins - auto; background color - #CF9B82;
- h3 heading of both sections must be centered, and have space between letters of 3px;
- first section: border of 2px solid black;
- second section: border of 2px solid #CF5958; bottom right and left radiuses worth of 10px;

          <section class="news">
               <h3>The Upcoming Events</h3>
               <ul>
                  <li>CBVA, Men's    AA,    Santa Cruz, August 3rd</li>
                  <li>Meeting, August 2nd</li>
                  <li>Release Alpha, July 30th</li>
                  <li>Meeting, June 2nd</li>
                  <li>Coachella Valley Music and Arts Festival, April 19th</li>
               </ul>
          </section>
          <section class="news">
               <h3>Updates on the main project</h3>
               <ul>
                   <li><a href="#">HTML and CSS updates, Jul - 29th</a></li>
                   <li><a href="#">The core of the JavaScript App, Jul - 25th</a></li>
                   <li><a href="#">Finished validating forms, Jul - 3rd</a></li>
               	<li><a href="#">HTML core document, Jun - 27th</a></li>
               </ul>       
          </section>
          
The output must be like:

![Required output](https://raw.github.com/Ksenja/My_Tut/master/img10.png)
      
[Answer](https://gist.github.com/Ksenja/4a571e1ff53ca01eafd6)


----------------------------------------------

## Conclusion 
And here we are, I can congratulate you on finishing this long guide, and lets summarize all of the above.
Now we know when applying styles efficiently you must consider several things - cascade, inheritance and specificity. Cascade is the way browser applies the style - it goes down through all rules and chooses the last one. But in the event of a conflict you can solve this by using higher specificity, though you have to assign it very carefully so that your code would not get too complex and heavy. Also we have taken a look at inheritance - which is the process of passing the same properties values form parents elements to their children. However, not all properties can be inherited. The most right way to apply inheritance - is to put your basic styles which will be inherited by descendants, on top of the others, so that you could always override them.
Then we concluded the section by presenting you the CSS important declaration, which must be used with caution, and some tips and tricks for you to avoid CSS conflicting rules.
I really hope you learned something from this guide, and sorry that it is so long :).

-----------------------------------------------

## Original Resources 

- [CSS: Core Concepts video course by James Williamson](http://www.lynda.com/Web-Interactive-CSS-tutorials/CSS-Core-Concepts/80435-2.html)
- [CSS3: The Missing Manual by David McFarland](http://www.amazon.com/CSS3-Missing-David-Sawyer-McFarland/dp/1449325947)

## Additional Learning Resources 

- [W3C list of properties](http://www.w3.org/TR/CSS21/propidx.html)
- [W3C CSS3 Selectors](http://www.w3.org/TR/css3-selectors/)

## Tools I used to create this guide 

- [Markable.in](http://markable.in/)
- [Shutter - Screenshot Tool](http://shutter-project.org/)
- [Sublime Text](http://www.sublimetext.com/)
- [Github](https://github.com/) and [Gist](https://gist.github.com/)

-------------------------------------------------

## Special Thanks ##

I want to say thanks to [Pedro Martins](http://www.codecademy.com/fl4m3ph03n1x) who pushed me on making this guide, got behind and helped me to publish it.:)

-------------------------------------------------

Folks, I really need your feedback on this guide! Feel free to put your comments here.

[web-fundamentals-track]: http://www.codecademy.com/tracks/web