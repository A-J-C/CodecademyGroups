I wouldn't be surprised if most of us got into Codecademy and programming while searching for ways to build a website.
I assume you have a basic grasp of HTML, CSS and Javascript.

In order to build a proper website, you will need a folder with the following contents:

 * Index.html
 * 404.html
 * offline.html
 * robots.txt
 * humans.txt
 * favicon.ico
 * sitename.appcache
 * CSS folder
      * stylesheet.css
      * ...
 * JS folder
      * vendor folder
           * jquery.js (example)
      * main.js
      * plugins.js
 * bin folder (for assorted files e.g. video)
      * video folder
      * downloads folder

You'll naturally want to make some changes, and that's normal.

Here's what my folder looks like:
![Website Contents][1]
App Cache
--
The `dann.appcache` file there is an [App Cache][2] file.
##### Note: You should totally check the [HTML5rocks App Cache tutorial][3].
By using it, you can give your users a way of browsing your website whithout internet connection.
This does have some downsides though, as you can accidentally give the user a cached copy of something they *shouldn't* have.
Here's an example `.appcache` file:

    CACHE MANIFEST

    CACHE:
    /favicon.ico

    NETWORK:
    /bin/downloads/

    FALLBACK:
    * /offline.html
The `.appcache` file MUST begin with `CACHE MANIFEST` in the first line. This is mandatory.
Now, the items under `CACHE` are the items to be cached for use in all offline situations.
See how I put the `favicon.ico` in there? That way, my website icon will always be cached and ready to go.
All the items under `NETWORK` are items that should not be cached and are only accessible with an internet connection.
The `FALLBACK` part defines items to be cached and shown in place of the ones not available.
Example:

    FALLBACK:
    *.html offline.html
    /img/ offline.png
Using this, `offline.png` will be served in place of any file not available in the `img` folder and offline.html will be served in place of all files with the `.html` file extension that are unavailable.

Also, if you add  the `manifest="sitename.appcache"` attribute to any page's `html` tag, it will automatically be cached.

In theory, you **can** cache your whole website, but you must keep in mind that there are limits to how much memory a website can cache.
Because of this, I advise to just have an `offline.html` and a an `offline.png` on the `FALLBACK` part.

##### Note: you can give any file extension to the manifest file, but the recommended one is `.appcache`.#####


robots.txt and humans.txt
--
The [robots.txt][4] file is used by search engines and robots to track your website.
The [humans.txt][5] file is a way of saying who developed the website and giving credit to the ones who built it and the tools used.
You should visit both these websites for more information.


What to put in index, 404 and offline.html
--
 * `index.html`

The `index.html` file is the homepage of your website.
Obviously, you are to build it yourself.
 * `offline.html`

The `offline.html` file is a page to be shown in case the user doesn't have an internet connection.
##### Note: In the `offline.html` file you should use inline CSS and Javascript. Also avoid using `meta` or `link` tags. #####
##### (Check the App Cache section above) #####
 * `404.html`

This is the page to be shown if the user encounter a '404' under your website.
##### Tip: make a template page from your `index.html`! #####

Javascript
--
The `js` folder should contain a `vendor` folder, where you can put Javascript libraries and frameworks.
Apart from the `vendor` folder, it should contain a `plugins.js` and a `main.js`, where you put plugins (duh) and your own code, respectively.

CSS
--
You should add your stylesheets to the `css` folder.
Also, if you have big stylesheets, I recommend [compressing them][6].
##### Note: when you compress/minify a file, it gains the `.min` file extension. Example: `main.js => main.min.js` #####
Favicon
--
A favicon is the little icon in the browser tab from the website.
You should make a png icon (32x32px) and turn it into an `.ico` file.
Unfortunately, there isn't much support for the `.ico` filetype, but there are various conversion tools online, like [this one][7]!

Your templates
--
You'll eventually reach a repetitive point where you have to copy/paste code from your other page to a new one.
A solution to this is to make template pages!
Here are some (but not all) types of templates you maight want to make:
 - Blank page
 - Splash page
 - Blog post

### Blank template ###
A blank page doesn't really mean *blank*, it means little to no UI.
This type of page is good for demos.
Here's an example from the [almighty CSS-Tricks][8]:
![See?][9]
##### [Source][10] #####
As you can see, the blank page has a small banner at the top with only four elements, all of which are non-intrusive. (Except maybe the ad)
It contains the ad, two links and text. No more. No less.
Here's a simpler Blank page:
![Nothing in it, though.][11]
Make sure to make it non-intrusive to whatever content you're adding.
Remember, this is a **template**.

### Splash page ###
A splash page is used to show off your content in **one page**. Most times you click an ad, you are directed into a splash page.
Here's an example:
![Dan uses Wordpress. Open your mouths in awe.][12]
##### [Source][13] #####
Since splash pages are flexible and don't take fixed, static forms from website to website, you should make it *yourself*. Be creative.
This is still a template. This means you may have *several* splash pages.
Like I just said, *be creative*.
### Blog post ###
Feel free to skip this if you don't have a blog.
A blog post template is easily both the hardest and easiest template you should make.
This because:
 - After having lots of blog posts, it will become harder to change each and every one.
 - They need space for content (the post)

A good solution for this is to not complicate the HTML part, and [use only CSS to change the looks][14] of it.
##### Tip: Make a different stylesheet for blog posts. E.g. `post.css` #####

Homepage
--
Your homepage works like a hub your content. More specifically, **all of it**.
Even if you want to restrict content from certain users, I recommend having a `forbidden.html` page, or whatever other means of clearance you want to add. Or not.
If you are primarily a blogger, I recommend having a post stream like [Tim Pietrusky][15] does.
On the other hand, if you are into making demos, I suggest making a recent-to-oldest list of your demos, like [this one][16].
##### Tip: Take as much time to develop your website to its fullest. It took me 2 days only to get my homepage working! #####

Domain
--
Your domain is where your website is located.
Example: your file `main.js` is located at `http(s)://website.com/js/main.js`
This is usually the most annoying part in website management.
To acquire a domain, you can use hosting websites like [GoDaddy][17].
There are also a **few** free domain hosting websites, like [DotTK][18], but *usually* they just allow for subdomain handling. (DotTK is an exception, check it out.)

Fin
--
If you need extra help or want to correct something, go ahead and comment.

**Remember: if you have to, start from scratch. It makes for good prectice and easily improves your website design and structure.**
I've had to restart *3 times* already.


  [1]: http://i.imgur.com/vC7ox.png
  [2]: http://www.w3schools.com/html/html5_app_cache.asp
  [3]: http://www.html5rocks.com/en/tutorials/appcache/beginner/
  [4]: http://robotstxt.org
  [5]: http://humanstxt.org
  [6]: http://www.minifycss.com/css-compressor/
  [7]: http://pngtoico.com
  [8]: http://css-tricks.com
  [9]: http://i.imgur.com/L6Zcu.png
  [10]: http://css-tricks.com/examples/MiddleBoxLinks/
  [11]: http://i.imgur.com/GjfOk.png
  [12]: http://i.imgur.com/Q1KUK.png
  [13]: http://danviv.net
  [14]: http://www.csszengarden.com/
  [15]: http://timpietrusky.com/
  [16]: http://fhtr.org/
  [17]: http://godaddy.com
  [18]: http://dot.tk