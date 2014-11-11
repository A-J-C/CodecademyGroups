----------

This Guide is a re-edition of some of the material from our [Useful Links][useful-links] resource. I realized that many questions were focused on a specific matter and that I could further improve the level of detail by making a different guide, but I never had the time. However, with the results from the second public [voting poll][poll-results] I decided that to create the [What do I need to create my first website?][first-website-guide] guide, that I needed this first so everything would fit together. I hope you all enjoy this guide and learn from it.

----------

## Introduction
Two of the most frequent question in the group are "Which tools do I use to code websites?" and "How do I share code?". In this brief guide I will introduce you to the most common tools used for these purposes and I will give you directions and links for you to explore more. There is one thing I want you to know right now: no tool is the best tool. **It all depends on your preferences**. Some people may recommend tool *A* because they like it more than tool *B* for a certain task, but you may disagree. 

Therefore in this guide **I will not pin-point you to the tools that you must use**, instead I will introduce you to some of the tools that **you can use** - the decision is always yours to make. At best I can tell you my personal preferences, but yours may be very different. In the end, I strongly recommend that you build your experience on trying as many tools as possible - it is the only way to know for sure if you like something in a highly subjective field as this.

Consequently, in the end I expect you to be able to answer the following questions:

- What tools can I use to write my code?
- What is the difference between text Editors and Integrated Development Environments (IDEs)?
- Should I use Text Editors or IDEs?
- How can I share my code with my team or friends?
- Should I use Pastebin Websites, Cloud Sync or a Revision Control System (RCS)?
- What are the advantages and disadvantages of using on-line tools?
 
By now you have probably realized that you are going to have a lot of reading and learning to do, so let us get started !

## Write your code
There are two main tools to write your code: Text Editors and IDEs. In the following sections of this chapter I will introduce you to them explaining their main strengths and what types of functionality you should demand from each. In the end I sum up with a mini conclusion that clarifies in which situations you should use each of the tools.

### Text Editors
Text Editors are simple programs that let you write text. If you are in Windows, an example is Notepad or Wordpad, if you are a Linux user then you probably have Gedit or Kate and if you are a Mac user then odds say you have TextEdit. Text Editors are most of the time very simple programs that simply allow you to write text and nothing more. However there is a broad set of Text Editors out there, which vary in their functionality. If you are coding with a Text Editor, you should at least demand the following functionalities out of it:

- Word completion, helps you type faster by guessing which word you want to type
- Snippets, help you code faster by creating complex code structures with just a few commands
- Highlight, helps you understand the code by giving a special color to some words and special tags
- Folding, makes code easier to understand by allowing you to temporarily hide some chunks of it
- Preview (optional), some Text Editors will launch your HTML files in your browser, allowing you to see the website on the go

In the end, Text Editors are suited for light applications, preferably Static websites (learn more about Dynamic and Static Websites in our guide [Website Hosting - Your Needs and Your Free Choices][website-hosting]) that are easy to make alone and do not require a back-end and only use the basics of HTML, CSS and JavaScript.

Not all Text Editors share these functionalities so you need to be careful when you choose one. You can check the Wiki lists of the most common Text Editors used:

- [Text Editors Wiki List 1](http://en.wikipedia.org/wiki/List_of_HTML_editors)
- [Text Editors Wiki List 2](http://en.wikipedia.org/wiki/List_of_text_editors)
 
If you have problems choosing from all of them there are a few Text Editors that I personally recommend:

- [Notepad++](http://notepad-plus-plus.org/)
- [Sublime Text](http://www.sublimetext.com/)
- [Kate](http://kate-editor.org/)
- [Brackets](http://brackets.io/)

 
### IDEs 
IDEs (Integrated Development Environments) are programs programs that are made of a pack of several tools and they aim at facilitating the activity of coding by having everything you need in a single program. IDEs are usually made of Text Editors (yes, every IDE has its own Text Editor, usually with all the features previously mentioned as necessary in the Text Editors section), Compilers, Interpreters, Debuggers, Previewers and much more. Furthermore IDEs usually support a wide variety of languages and their complex nature makes them tools suited for developing Dynamic Websites (learn more about Dynamic and Static Websites in our tutorial [Website Hosting - Your Needs and Your Free Choices][website-hosting]).

They are complex tools and usually have a higher and steeper learning curve when compared to the simple Text Editors (this means that you need more time to learn how to use them properly). Nevertheless, IDEs are more powerful than Text Editors and they usually allow the users to build more complex applications and websites due to the fact that they usually have an advanced set of tools to work with back-end languages such as PHP, Ruby, Python, Java and Scala.

Following is a list of the most common IDEs used:

- [IDE comparison list Wiki 1](http://en.wikipedia.org/wiki/Comparison_of_integrated_development_environments)
- [A Beginner's Guide to Integrated Development Environments](http://mashable.com/2010/10/06/ide-guide/)

Once again, if you are having trouble choosing from the lists, here are my personal choices:

- [Netbeans](https://netbeans.org/)
- [Aptana](http://www.aptana.com/)
- [Eclipse](http://www.eclipse.org/)

### Summing up, when to use Text Editors and IDEs?
Text Editors are simple tools fitted to make Static Websites with basic knowledge of HTML, CSS and JavaScript. Usually such websites are made by a team of only one person and so synchronization of files between a team is not a problem. Here the simplicity of Text Editors is an advantage.

IDEs are complex tools, designed to accommodate the development of complex projects such as Dynamic Websites. Some IDEs also have integration with tools that help you synchronize your code with a team of several elements (such as NetBeans) thus making it easier to manage big and complex projects. IDEs take longer to learn but are more powerful because they have arrays of tools fitted to help you code the back-end of a website using languages like PHP, Ruby, Python, Java and Scala. Although IDEs can also be used to develop Static Websites, you may feel overwhelmed by all the tools and complexity generated to do so.

In the end, your choice to rather use Text Editors or IDEs should depend on:

- the complexity of your project
    - Static Websites can easily be done using simple Text Editors
    - Dynamic Websites require the use of IDEs
- the time available that you have to learn the tool you selected
    - is the tool too hard to learn?
    - does the tool have a good documentation and on-line help? 

## Share your code
There are three main ways to share your code: using websites built for that purpose, programs like that store your files in the cloud, or using complex and powerful tools called Revision Control Systems (RCSs). In this chapter we will briefly introduce you to them as well as provide a small mini-conclusion in the end that will compare their strengths and weaknesses as well.

### On-line pastebins
This is usually made using pastebins: websites where you can either temporarily or permanently paste a snippet of code and make it available to everyone through a URL. Using this method the viewers are only able to view your content and are unable to change it. It is good to show your projects to your friends or community if the project does not have a big number of files that need to be pasted on-line: if such happens the viewers may get lost among all the URLs needed.

If you opt for this solution, there are a few functionalities that I strongly recommend you activate in the website:

- Highlight depending on language, for the same reasons mentioned in the Text Editor Section
- Line Numbers (optional), helps some viewers watching the file
- An automatic copy/paste button (optional), makes it easier when the files that need to be copied are long
 
Once again there are many websites to fulfill this need. Here are a few lists that you can use as a reference:

- [25 Handy Tools To Paste And Share Your Code Snippets](http://www.1stwebdesigner.com/freebies/paste-share-code-snippets/)
- [4 Alternatives That May Be Better Than Pastebin](http://www.makeuseof.com/tag/4-alternatives-that-may-be-better-than-pastebin/)
- [alternativeTo PasteBin](http://alternativeto.net/software/pastebin/)
- [A list of 50 sites similar to: pastebin.com](http://www.similarsitesearch.com/alternatives-to/pastebin.com)
 
Once again, if you feel lost, here are my personal preferences which I recommend:

- [TinyPaste](http://tny.cz/)
- [KDE paste](http://paste.kde.org/)
- [Hastebin](http://www.hastebin.com/about.md)

### Cloud sync storage  
This solution usually involves installing a software on your machine that synchronizes your folders and files with an on-line cloud, having an account on a certain service and upload your files, or sometimes both. Solutions pertaining to this category include services like Dropbox or Google Drive. Usually they have an option that creates a public link to specific files and its this option that you can use to share your work. These services can allow your viewers to change the content of the file or not depending on the service and the permissions given to the viewers. 

However some services may ask you to pay a fee or they limit the number of views that can be done, thus having a large team of people can become a problem. Furthermore, some of these services have weak synchronization capabilities: when multiple people edit the same file, multiple conflicting versions are created or lost. Consequently, using this service is once again only good for small projects with a small team or medium projects with a small team. 

Following are lists that compare these services:

- [Google Drive vs. Dropbox, SkyDrive, SugarSync, and others: a cloud sync storage face-off](http://www.theverge.com/2012/4/24/2954960/google-drive-dropbox-skydrive-sugarsync-cloud-storage-competition)
- [Dropbox Alternatives and Competitors: Dropbox vs Other Online File Sharing and Storage Tools](http://theprofessionalspoint.blogspot.pt/2013/03/dropbox-alternatives-and-competitors.html)

And here are my personal choices:

- [Dropbox](https://www.dropbox.com/)
- [Ubuntu One](https://one.ubuntu.com/)
- [Google Drive](https://accounts.google.com/ServiceLogin?service=wise&passive=1209600&continue=https://drive.google.com/%23&followup=https://drive.google.com/&ltmpl=drive)

### RCSs
RCSs are programs that allow you to easily synchronize, backup and share multiple versions of files. These are the most complex and complete tools when it comes to sharing code. They allow other people to make changes to the project without compromising its integrity, and if you do not like the changes you do not have to worry because these systems always have a backup version. One such system is Git. For a more detailed definition and overview on RCSs I strongly recommend you to read our tutorial [Revision Control System - Git (how install, how to use and competition)][git-tut], which cover all main aspects of an RCS system, while also giving a tour on Git (officially used and supported by CodeCademy) and some of its competitors.

Summing up the article, these systems can be quite complex and hard to learn. However there are many resources out there to help you, and there are also usually interfaces and IDE integration to ease your job. If you are working on a Dynamic Website and you wish to share your content with a team or with the world, this is definitely the tool you should use.

### Summing up, when to use pastebins, Cloud sync and RCS?
Pastebins are the easiest way to share a code snippet with someone. Most of the time the websites do not even require you to have a account created, and you can choose for how long your code will be available to the public. This method is idea for small projects that you do alone or for a project with a very small team (2 people at maximum). It does not allow for changes in the files, relies solely on the copy-paste method and it is free. In fact, some services even offer you money, like TinyPaste. It also does not deal with synchronization, backup or version control: everything must be done by the users. Ideal for Static Websites or when you need to post a small snippet of code and show it in a highlighted user-friendly way.

Cloud Sync solutions are a little bit more complete and complex. They all require you to create an account and some need you to have a specific software installed in your local machines. This solution allows you to share files by means of a public link or public folder, and it may or may not allow the readers to change and update the content. However, some services may have a limit on viewers backup system is not guaranteed (depends on the cloud solution being used, for example, Dropbox has a backup system, but Google Drive does not) and controlling different versions of the same file is fragile and often disastrous, leading to conflicting copies or lost data. Consequently, this solution can be seen as a mid term between Pastebins and RCSs. I recommend it for medium projects with small teams (of 2 to 4 people), but there must be coordination so that multiple people do not edit one file at the same time in order to reduce the chance of having conflicting versions. Recommended for both Static Websites and Dynamic Websites. 

Finally we have RCSs. These tools are both complex and complete, and may also share integration with IDEs. They have everything the other solutions have, plus backup and version control of files. It is the only recommended solution for teams with more than 5 people working actively and it is recommended for both Static and Dynamic Websites, both big and medium. It may be overkill for a small project though, but that is your call.

## On-line Tools
Now that you know the difference between Text Editors and IDEs, and that you also know multiple ways to share your code, it is time to talk about web tools. These web tools are on-line code editors with many of the functionalities of the previously seen Text Editors and IDEs. They require an always on-line Internet connection and an account for you to create and manage your projects but they have the advantages of:

- You can access your work in any place (even in computers that you do not own) as long as you have an Internet connection;
- These tools have a strong focus on community, so it is easier to share and announce your work;
- Strong community focus also makes it easier for you to help others and find help;
- Interfaces easy to understand and specifically directed at Website making.

However, this solution also have a few disadvantages:

- You must have an Internet connection **at all times** to work;
- They are not as powerful as IDEs and RCVs combined together;
- Some are very limited and do not allow you to import JavaScript and CSS libraries in an organized nor consistent manner, forcing you to mix everything into a single file.
- Some of these tools have severe problems with browser compatibility, they may not work on all browsers or if they do, they may have issues. 

There are also several on-line code editors that you can choose from. Following is are a few lists:

- [10+ useful online code editors](http://www.catswhocode.com/blog/10-useful-online-code-editors)
- [10 HTML & CSS Online Code Editors for Web Developers](http://www.awwwards.com/10-html-css-online-code-editors-for-web-developers.html)
 
When it comes to this matter, I have very small experience, thus I cannot recommend anything specifically. I can however mention all the on-line code editors that the users of our group have suggested, hoping that you have dun trying them out:

- [jsbin](http://jsbin.com/)
- [jsfiddle](http://jsfiddle.net/)
- [CodePen](http://codepen.io/pen/)
- [Mozilla Thimble](https://thimble.webmaker.org/)
- [CSSDesk](http://cssdesk.com/)
- [Plunker](http://plnkr.co/)
- [ShiftIDE](https://shiftedit.net/login)
- [Cloud9 IDE](https://c9.io/)
- [Codeanywhere](https://codeanywhere.net/)

## Conclusion
This article is meant to be a small introduction to the tools you can use to build your own projects and to share them. Always remember that **there is no "must use tool"**, it always depends on the size of your project, your team and your needs. 

By now you should know that you can write your code using Text Editors, IDEs or on-line code editors. IDEs are more powerful tools than Text Editors and thus allow you to manage bigger projects and teams. Whether you should use a simple Text Editor or an IDE its up to you to decide depending on the size of you team, project and time available to learn the tools. 

You can share your code with your community by using Pastebin Websites, Cloud Sync tools, a RCS system or by taking advantage of the community tools provided by on-line code editors. Pastebin Websites should be used on small projects with a small team (1-2 members) or to temporarily paste a code snippet and make it available to everyone through an URL. Cloud Sync tools can be used by teams of 2-4 members and allow for easier sharing than Pastebin Websites, but you must be careful with conflicting file versions, backups and limit of views. Finally, RCS systems can be used in any occasion (though they are probably overkill for a small project) and they are a worthy investment in time and effort.

Finally, on-line tools share many advantages and disadvantages, all of them precisely enumerated in the *On-line Tools* Section.

Now that we have concluded this guide you probably feel lost among all the possibilities. There is no Holly Grail here - you have to try them on your own so you can make an informed choice. If you need help, just start by trying my recommendations and move onwards from there. 

## Special Thanks

- [WaffleGnome](http://www.codecademy.com/wafflegnome), for starting the creation of the [Useful Links][useful-links] resource, which has originated this guide.
- [Ksenja](http://www.codecademy.com/ksenja), for the support that she gave me!
 
[useful-links]: http://www.codecademy.com/groups/html-projects/discussions/51675caa9e630cd33b0016df
[poll-results]: http://awesomescreenshot.com/0e51hi143e
[first-website-guide]: http://www.codecademy.com/groups/html-projects/discussions/51e69fe27c82ca29510040c3
[website-hosting]: http://www.codecademy.com/groups/html-projects/discussions/5167394881c2702060000d1f
[git-tut]: http://www.codecademy.com/groups/html-projects/discussions/5177d3a1758e99b46e003d6a#