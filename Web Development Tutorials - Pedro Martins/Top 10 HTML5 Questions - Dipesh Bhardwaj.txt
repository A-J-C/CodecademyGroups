## Prior Requirements:

- [Web Fundamentals][web_fundamentals]

## Introduction
So maybe you are done with Codecademy and want to get a job making web pages. Maybe you think you master HTML and you want to see what an employer would ask you in a job interview. Even if you are just curious and wish to learn more HTML5 tricks, you came to the right place.
This article is for people who want to prepare themselves for a job interview, or for people who wish to test their HTML mastery and learn new skills. Here we will discuss the top ten HTML5 questions asked in interviews and we will provide each one with a concise and clean answer.

1. What's new HTML 5 DocType and Charset?
2. How can we embed Audio in HTML 5?
3. How can we embed Video in HTML 5?
4. What are the new media elements in HTML 5 other than audio and video?
5. What is the usage of canvas Element in HTML 5?
6. What are the different types of storage in HTML 5?
7. What are the new Form Elements introduced in HTML 5?
8. What are the deprecated Elements in HTML5 from HTML4?
9. What are the new APIs provided by HTML 5 standard?
10. What is the difference between HTML 5 Application Cache and regular HTML Browser Cache?

By the end of the article you should have a grasp on your main HTML weaknesses. Then it's only up to you to improve them and become a better coder. **Also, don't forget to check the sources section, where you'll find more links and information to help you complement what you've learned in the questions.**

## Questions

### 1. What's new HTML 5 DocType and Charset?

As HTML 5 is now not a subset of SGML, its DocType is simplified as follows:

    <!doctype html>

And HTML 5 uses UTF-8 encoding as follows:
   

    <meta charset="UTF-8">

### 2. How can we embed Audio in HTML 5?

HTML 5 comes with a standard way of embedding audio files. Supported audio formats are MP3, Wav and Ogg.

    <audio controls>
    <source src="jamshed.mp3" type="audio/mpeg">
    Your browser doesn't support audio embedding feature.
    </audio>

### 3. How can we embed Video in HTML 5?

Same like audio, HTML 5 defined standard way of embedding video files. Supported video formats are MP4, WebM and Ogg.

    <video width="450" height="340" controls>
    <source src="jamshed.mp4" type="video/mp4">
    Your browser does'nt support video embedding feature.
    </video>

### 4. What are the new media elements in HTML 5 other than audio and video?

HTML 5 has strong support for media. Other than audio and video tags, it comes with the following tags:

 - `<embed>` acts as a container for external application.
 - `<track>` defines text track for media.
 - `<source>` is helpful for multiple media sources for audio and video.

### 5. What is the usage of canvas Element in HTML 5?

`<canvas>` is an element in HTML5 which we can use to draw graphics with the help of scripting (which is most probably JavaScript). 
This element behaves like a container for graphics and rest of the things will be done by scripting. We can draw images, graphs and a bit of animations etc. using `<canvas>` element.

    <canvas id="canvas1" width="300" height="100">
    </canvas>

### 6. What are the different types of storage in HTML 5?

HTML 5 has the capability to store data locally. Previously, it was done with the help of cookies. The exciting thing about this storage is that it's fast as well as secure.

There are two different objects which can be used to store data:

 - localStorage object stores data for a longer period of time even if the browser is closed.
 - sessionStorage object stores data for a specific session.

### 7. What are the new Form Elements introduced in HTML 5?

There are a number of new form elements that have been introduced in HTML 5 as follows:

- datalist
- datetime
- output
- keygen
- date
- month
- week
- time
- number
- range
- email
- url

### 8. What are the deprecated Elements in HTML5 from HTML4?

Elements that are deprecated from HTML 4 to HTML 5 are:

- frame
- frameset
- noframe
- applet
- big
- center
- basefront

### 9. What are the new APIs provided by HTML 5 standard?

HTML 5 standard comes with a number of new APIs. Few of them are as follows:

- Media API
- Text Track API
- Application Cache API
- User Interaction
- Data Transfer API
- Command API
- Constraint Validation API
- History API
and many more....

### 10. What is the difference between HTML 5 Application Cache and regular HTML Browser Cache?

One of the key features of HTML 5 is "Application Cache" that enables us to make an offline version of a web application. It allows to fetch few or all of website contents such as HTML files, CSS, images, JavaScript, etc. locally. This feature speeds up the site performance. This is achieved with the help of a manifest file defined as follows:

    <!doctype html>
    <html manifest="example.appcache">
    .....
    </html>

As compared with traditional browser caching, it's not compulsory for the user to visit website contents to be cached.

## Conclusion
Hopefully by now you acquired some taste of what an employer might ask in an interview. Even if that was not your goal, I am quite sure that learning how to add video and sound to your HTML documents will make everything a lot cooler. Still, feel free to make suggestions, we are always open to improvements!

## Sources

- [Top 10 HTML 5 Interview Questions](http://www.codeproject.com/Articles/586359/Topplus10plusHTMLplus5plusInterviewplusQuestions): for the original article
- [HTML5 Introduction](http://www.w3schools.com/html/html5_intro.asp): for an introduction to HTML5
- [28 HTML5 Features, Tips, and Techniques you Must Know](http://net.tutsplus.com/tutorials/html-css-techniques/25-html5-features-tips-and-techniques-you-must-know/): for more HTML5 stuff that you should know!
- [HTML Dog](http://www.htmldog.com/):  web designer’s resource for everything HTML, CSS, and JavaScript!
- [Web Platform](http://docs.webplatform.org/wiki/Main_Page): for more goodies on web technologies !

## Credits

- [Pedro Martins](http://www.codecademy.com/fl4m3ph03n1x): for adding content, reviewing and updating this article

[web_fundamentals]: http://www.codecademy.com/tracks/web