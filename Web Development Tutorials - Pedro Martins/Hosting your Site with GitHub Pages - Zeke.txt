In this (unofficial) tutorial, we'll learn how to host a site with [Github Pages](https://pages.github.com/). 
This guide assumes you're running Linux (or using a command line), and you're going to need to be signed into [Github](https://github.com) for this to work. 

 1. Head into the upper right corner and add a new repository: ![](http://s13.postimg.org/ikhmpllsn/image.png)

 2. Name the repository [*your username*].github.io: ![](http://s27.postimg.org/5w0nlyw4j/image.png) You can see I'm getting an error message; that's because I'm already using Github Pages to host something else. Also, you need to check "Initialize this repository with a README", or it won't work. 

 3. Next, open up your command line, `cd` into the folder where you're planning on storing your project, and type this in: `git clone https://github.com/username/username.github.io`, replacing *username* with your Github username: ![](http://s24.postimg.org/tpb6iwpat/image.png)

 4. `cd` into your new folder. 

 5. Copy/paste all of your files you want to show up into the folder named [*username*].github.io. For me, I've got an `index.html` and a `style.css` file, as well as a couple of photos: ![](http://s22.postimg.org/rr9h6pe1t/image.png) 

 6. Type in `git add --all`

 7. Type in `git commit -m "Initial commit"`

 8. Type in `git push`. It'll ask you for your username and password; enter both: ![](http://s29.postimg.org/ayqpp4y6v/image.png)

**That's it!**

If you ever need to update a file, repeat the last 3 steps, and your update will be visible almost instantly. 

It shouldn't take longer than 10-15 minutes before your site is live, however once it's up and running, updates will generally be pushed within 30 seconds. 

If you can't get your site up following my instructions above, please reply below, and I'll try to help. 