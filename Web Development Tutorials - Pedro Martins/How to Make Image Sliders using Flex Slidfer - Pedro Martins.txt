## Prior Requirements:

- [Web Fundamentals](http://www.codecademy.com/tracks/web) 
- [Javascript](http://www.codecademy.com/tracks/javascript)
- [JQuery](http://www.codecademy.com/tracks/jquery)

----------

Once upon a time, a little phoenix was searching Codecademy's forums for discussions and wanted to help people. Most discussions related trivial problems with over 9000 answers on how to solve a simple problem, but among those discussions there was a poor fellow that was asking a question on how to use flex, and no one was able to help him. Not long after, the discussion went forgotten into oblivion by most people... most people, but not the little phoenix.

----------

## Introduction
Imagine that you have a set of images and you want to display them in your website, using sliders and click-able buttons. You may even want to use a carousel, like in the image bellow, but you are new and you have no idea on how to do it. If that is your case, you came to the right place.

[![slider_example](https://dl.dropboxusercontent.com/u/785815/flex_tutorial/image/presentation_slider.gif)](http://www.woothemes.com/flexslider/)

Before we start, it is important that you have completed the following Codecademy tracks:

- [Web Fundamentals](http://www.codecademy.com/tracks/web) 
- [Javascript](http://www.codecademy.com/tracks/javascript)
- [JQuery](http://www.codecademy.com/tracks/jquery)

By the end of this tutorial you should know:

- What is Flex Slider?
- How to create image sliders
- How to create image carousels
- How to have an image slider synchronized with an image carousel
- Flex Slider Main problems

## Flex slider
### What is Flex Slider?
Fex Slider is a jQuery plugin that enables you to make the image and video sliders, like the one showed above. (you can actually check the official site listed bellow for a live example!).
Flex Video APIs for Vimeo and wistia will not be discussed here, this tutorial is only going to focus on teaching you the basic concepts of image sliders, image carousels and how to synchronize them properly.

### Installing Flex Slider in your project

1. First you need to have a folder for your project, I called mine mySlider. This is the folder that is going to contain all the code of this little project.
2. Inside this folder create four additional folders: html, css, image and library. As you can guess by the name, the folder html will contain our HTML code, css will contain our css files, image will contain our images and library will be the folder where we will place the libraries and plugins we use, in this case, the Flex installation files.
3. Download Flex from the [official website](http://www.woothemes.com/flexslider/) and extract its contents to a new location.
4. Inside the folder you have just extracted there is a lot of stuff. Copy everything inside it except for the demo folder into a new folder and call it "flex". Then place this newly created folder (flex) inside the library folder you have previously created.

Now you have flex ready for your project. However, now your project needs to know that you are going to use Flex on it. This is done in your HTML files where you plan on using Flex. This is done in the **head** tag of your HTML file:

    <head>
        <meta content="charset=utf-8">
        <title>FlexSlider Basic Slider 1</title>
    
        <!-- The paths in these three lines MUST be correct, and point to 
        the places where jquery and flex libraries are!
        -->
        <link rel="stylesheet" href="../library/flex/flexslider.css" type="text/css">
        <script src="https://ajax.googleapis.com/ajax/libs/jquery/1.6.2/jquery.min.js"></script>
        <script src="../library/flex/jquery.flexslider.js"></script>

        <!--Dont forget to include your customization files correctly as well-->
        <script src="../javascript/index_1.js" type="text/javascript"></script>
        <link rel="stylesheet" href="../css/index_1.css" type="text/css">
    </head>

At first this might look like a lot of complex code, but we will go through it one line at a time. 

The first two lines define the charset and the title of your page. These are standard and very common in all the HTML files, even those that do not use Flex. If you have trouble remembering this you can visit the Web Fundamentals track, as this is actually covered there :D

The next relevant lines are: 

    <link rel="stylesheet" href="../library/flex/flexslider.css" type="text/css">
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/1.6.2/jquery.min.js"></script>
    <script src="../library/flex/jquery.flexslider.js"></script>

These are the lines that actually link your HTML file to the Flex library. The first line imports Flex's css files. It defines things like size and style. 
The second line actually imports another required library, the jQuery library via Google URL. Now you could have a direct link to a file in one of your folders, but for this case I decided to dynamically download the requirements.
The last last, is the location of Flex's javascript code, it defined what happens when you click on buttons and other more complex stuff like callback APIs.
For your project to work correctly, it is **critical** that these three lines have the correct paths. If one of them does not have the correct path, your website won't implement Flex Slider at all.

Last but not least, we have our own customization files:

     <script src="../javascript/YOUR_JS_FILE" type="text/javascript"></script>
     <link rel="stylesheet" href="../css/index_1.css" type="text/css">

These files are NOT part of the Flex library, they are instead files that we use to customize our own project.
The first file (javascript import) is the place where you will have all your Flex Slider customizations. The second (css import) is the file that will define sizes, positions, colors, and every other artistic or design style you add to the project.

**As in before, make sure the paths are correct!**

If all these concepts look a little fuzzy to you right now, don't worry, we'll jump into some real examples now and hopefully you will understand better !

### Your first Image Slider
So, now you are finally about to learn how to use Flex to make image sliders. By the end of this chapter, this is what you should have (**click it to see the website!**)

[![slider1](https://dl.dropboxusercontent.com/u/785815/flex_tutorial/image/slider1.gif)](https://dl.dropboxusercontent.com/u/785815/flex_tutorial/html/index_1.html)

To make the slider you previously saw (**click the image!**) there are three things we will need:

- a HTML file for our images
- a javascript file for our Flex customizations
- a CSS file to center the slider and resize the images

To use Flex slider correctly, you only need the HTML file and the javascript customization file. So those will be our priories. The CSS files is something extra I added to make things look pretty in the end :P

#### HTML 
To add a simple image slider to your webpage like the one you saw, you only need to paste the following code inside the body tags:

    <div class="flexslider">
		<ul class="slides">
			<li>
				<img src="../image/wallpaper-346615.jpg" />
			</li>
			<li>
				<img src="../image/wallpaper-515363.jpg" />
			</li>
			<li>
				<img src="../image/wallpaper-560399.jpg" />
			</li>
			<li>
				<img src="../image/wallpaper-687175.jpg" />
			</li>
			<li>
				<img src="../image/wallpaper-1575180.jpg" />
			</li>
			<li>
				<img src="../image/wallpaper-403281.jpg" />
			</li>
		</ul>
	</div>

As you can see, all that I used was a simple div tag, with a unordered list containing my chosen images inside. The div and the list however must belong to specific class types, such as the *flexslider* and the *slides* classes respectively. This is necessary so the Flex library can recognize them and do the necessary work to present the images as an image slider.

#### Javascript
Now that we have our HTML done, we can safely move on to our flex customization file. To start, we will define an empty customization and simply go along with the defaults. Inside your javascript folder create a javascript file with the following code:

    $(window).load(function() {
        $('.flexslider').flexslider();
    });

This basically loads flex. With these two files (the HTML and the Javascript) you can now see your first image slider ! However, the images will be way too big, and the slider will not be centered. To fix that I have created a simple CSS file.

#### CSS 
So, now that you have your precious slider working, it would be nice to have it centered and a little bit smaller. To fix that I created a CSS file inside the CSS folder with the following:

    .flexslider {
    	width: 55%;
    	margin-top: auto;
    	margin-right: auto;
    	margin-left: auto;
    }

Quite simple don't you think? This file gets all flexslider objects, reduces them to 55% of their width and then centers them. Piece of cake!

The full source code is available here:

- [index_1.html](http://tny.cz/e169cbe7)
- [index_1.js](http://tny.cz/a47d0b3a)
- [index_1.css](http://tny.cz/20dc3cc0)

### Expanding our Image Slider
So now that you have a simple image slider you may want to do a few modifications on your own. Maybe you and the slide animation to be different, and maybe you don't want those arrows on each side of the image. 
Maybe you want a caption and maybe you want to do something when you click an image or swap it. 

Flex has a rich API that allows you to do that and a lot more. To see their API you should check the [official site](http://www.woothemes.com/flexslider/), where they are give you examples on how to use it.

To prove this concept I made another animation, this time using Assassin's Creed as a main theme. If you look closely, there are a few different things:

- Images 1 and 2 have a caption
- Image 3 has no caption
- There are no arrows on the sides of the images

[![slider2](https://dl.dropboxusercontent.com/u/785815/flex_tutorial/image/slider2.gif)](https://dl.dropboxusercontent.com/u/785815/flex_tutorial/html/index_2.html)

This example is actually explain in their documentation, but if you do not want to read the entire thing, here are the relevant parts of the HTML, javascript and CSS files I used.

#### HTML
To make this special image slider I had to use the *flex-container* class. This affected the CSS file a lot as you will see in a minute.

    <div class="flex-container">
		<div class="flexslider">
			<ul class="slides">
				<li>
					<img src="../image/Altair.jpg" />
					<p class="flex-caption">This is an image of the first Assassins Creed with Altair</p>
				</li>
				<li>
					<img src="../image/Ezio.jpg" />
					<p class="flex-caption">This is from the second saga, with Ezio!</p>
				</li>
				<li>
					<img src="../image/Connor.png" />
				</li>
			</ul>
		</div>
	</div>

#### Javascript
In this case we made a little of customization. Here we specify that the animation will be a slide, instead of fade, and that the container controller is the class flex-container.

    $(window).load(function() {
        $('.flexslider').flexslider({
            animation: "slide",
            controlsContainer: ".flex-container"
        });
    });

#### CSS
Here the new class *flex-container* made me take a few drastic positions. Because *margin: auto* was no longer working properly I had to make its position absolute and set the *margin-left* property manually. The good thing about using *em* instead of *px* is that *em* is relative to the proportions of your screen, so you should always see the image centered no matter the size of the screen.

Another funny thing was the bottom margin of the *flexslider*, which I had to change to 0px because I wanted them to be closer. 

    .flex-container {
        position: absolute;
        width: 50%;
        margin-left: 30em;
    }

    .flexslider{
        margin-bottom: 0px;
    }

You can check the source code here:

- [index_2.html](http://tny.cz/c4f0f901)
- [index_2.js](http://tny.cz/6d2c6889)
- [index_2.css](http://tny.cz/af31f1dc)

### More than one image slider per page
Why stop here? Flex allows you to define multiple slider per page and to define them as primary and secondary as well. Check the full code bellow:

- [index_3.html](http://tny.cz/1a0c3da4)
- [index_3.js](http://tny.cz/544b6e24)
- [index_3.css](http://tny.cz/92431e52)


[![slider_example](https://dl.dropboxusercontent.com/u/785815/flex_tutorial/image/slider3.1.gif)](https://dl.dropboxusercontent.com/u/785815/flex_tutorial/html/index_3.html)

[![slider_example](https://dl.dropboxusercontent.com/u/785815/flex_tutorial/image/slider3.2.gif)](https://dl.dropboxusercontent.com/u/785815/flex_tutorial/html/index_3.html)

### Image Sliders synchronized with Carousels
Now that you know how to make simple images sliders, it is time to move up to the next step synchronizing them with carousels. Carousels are usually bellow image sliders like in the image below:


[![slider4](https://dl.dropboxusercontent.com/u/785815/flex_tutorial/image/slider4.gif)](https://dl.dropboxusercontent.com/u/785815/flex_tutorial/html/index_4.html)

Let us now take a look into the two most important files, the HTML and the Javascript:

#### HTML

    <div id="slider" class="flexslider">
		<ul class="slides">
			<li>
				<img src="../image/car1.jpg" />
			</li>
			<!-- Other images -->
		</ul>
	</div>
	<div id="carousel" class="flexslider">
		<ul class="slides">
			<li>
				<img src="../image/car1.jpg" />
			</li>
			<!-- Other images -->
		</ul>
	</div>

As you can see, few things actually change from our previous example. It is like having two sliders, however the ids do all the magic. One slider has an id of *slider*, while the other has an id of *carousel*. And that is all for the HTML.

#### Javascript
//Target sliders individually with different properties

    $(window).load(function() {
        // The slider being synced must be initialized first
        $('#carousel').flexslider({
            animation: "slide",
            controlNav: false,
            animationLoop: false,
            slideshow: false,
            itemWidth: 210,
            itemMargin: 5,
            asNavFor: '#slider'
        });
			
        $('#slider').flexslider({
            animation: "slide",
            controlNav: false,
            animationLoop: false,
            slideshow: false,
            sync: "#carousel"
        });
    });

This part is more tricky however.  In this example, we set the custom specifications for each slider and carousel. Flex allows you to do this through the magic of jQuery Id selectors as you can see. For a range of all the customizations, see the [official documentation](http://www.woothemes.com/flexslider/).

You can check the source code here:

- [index_4.html](http://tny.cz/097ddb78)
- [index_4.js](http://tny.cz/12cb4706)
- [index_4.css](http://tny.cz/882553f7)

### Flex Problems with images
Now that you have seen and made multiple sliders, it is time for you to know Flex's limitations:
 - The most important one, its how difficult it is to show images of different sizes and width-height rations in flex. If you attempt to do so, the images will not be centered, and the Flex slider will constantly change size based on the image it is showing thus looking horrible. The best solution for this problem is to make sure all your images have the same size, it is not by accident that image 6 of slider 1 has 2 black bars, one at the top and one at the bottom.

[![slider5](https://dl.dropboxusercontent.com/u/785815/flex_tutorial/image/slider5.gif)](https://dl.dropboxusercontent.com/u/785815/flex_tutorial/html/index_5.html)

Source code:

- [index_5.html](http://tny.cz/4b26f9b2)
- [index_1.js reuse](http://tny.cz/a47d0b3a)
- [index_1.css reuse](http://tny.cz/20dc3cc0)

- If you need anything more advanced, like a new UI style, odds are that you will have to change the library's code itself. Although many people like doing it, **it totally defeats the purpose of using a library**. Libraries are meant to be reusable pieces of code. If you go on an change it for every case, it is not reusable anymore - not to mention the update problems. Furthermore many times Flex's UI styles override your own styles without any warning, thus making it very difficult to detect problems when coding CSS.
- Finding and using information about Flex is quite hard. Aside from a few blogs and the original documentation that all explain pretty much the same thing, you won't find an overwhelming number of people with the knowledge able to support you. The best case in such situations is to ask in forums, such as [stackoverflow](http://stackoverflow.com/).

## Conclusion
Overall Flex is an easy to use tool for the most common types of images sliders. If you use the templates, making an image slider becomes easy and effortless because it places no barrier at all in the levels of knowledge about HTML. When it comes to Javascript however, you really must read the documentation to achieve your goals, and when it comes to CSS you simply have to pray that your styles do not conflict with those being used on the library.

Flex also places restrictions in the images width-height ratio. If you want a slider to show different images with different rations you have to do some serious hacking in your CSS, and even then the problem is not guaranteed to be fixed without changing the library's code.

In the end, we can conclude that Flex is suited for the most common uses of image sliders, but lacks community support beyond the official documentation and is hard for beginners to use with advanced customization settings.

## Sources

- http://www.woothemes.com/flexslider/
- http://return-true.com/2012/04/installing-woothemes-flexslider-into-your-wordpress-theme/
- http://wallbase.cc/toplist

## Special Thanks to Projects

- [Krut](http://krut.sourceforge.net/): a free screen recorder that helped me a lot. Without it I would not have been able to create the .mov files that later originated the GIFs in the tutorial. 
- [online-convert](http://www.online-convert.com/): the only online and decent free GIF converter tool that I found. Without it, I would not have been able to post high quality GIFs in the tutorial.
- [tinypaste](http://tny.cz/): for allowing to place my source code online and still make money out of it xD