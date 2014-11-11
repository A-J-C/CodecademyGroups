## Introduction
So far one thing that I have realized is that every beginner in Codecademy either doesn't know how to use Git or finds it too hard. Being the only contact that Codecademy allows us to share in our profile (besides a personal page that 90% of us don't have) and given in mind the significant benefits that Git brings to the table when developing projects with several people, I feel it is important that everyone should at least have a basic knowledge about Git, its tools (including GUI interfaces) and some of its alternatives as well.
Thus, by the end of this tutorial, you should be able to answer the following questions on your own:

- What is Git?
- What is the difference between Git and GitHub?
- Are there any alternatives to Git?
- Are there any alternatives to GitHub?

## What is a Revision Control System (RCS)?
Revision control systems, also known as version control or source control systems, are programs used to manage multiple versions of files. These files can be text, documents, images, programs or pretty much anything else. 
These systems usually allow people to lock files (keeping other members from changing them), track changes to files while keeping a change log, merge different sections of a file edited by multiple people, automatically resolve conflicts in files that were edited by multiple people and more, depending on the system you use.
If you are working alone on a project, you don't need a RCS, however if you are working with multiple people, you'll need to keep track of their work as well as track the changes that they do to your files.

An RCS is usually installed in a server connected to the internet. This way, when people want to send their work to the RCS, they **push** it to the server, and when they wish to get the latest version of the code, they **pull** it from the server.
Therefore, if you wish to have your work always available in a server, you need a [web host](http://www.codecademy.com/groups/html-projects/discussions/5167394881c2702060000d1f) that can give you a machine to host your stuff.

### Git
#### What is Git?
Git is one of many RCS that there are out there. Git has the ability to be distributed (meaning that your work can be saved in various machines, each machine containing a part of the total) and it has been raising the last few years. Like Git there are many other RCS you can use, here is a small list with the more common ones:

#### Git Competitors

- [Concurrent Versions System](http://www.nongnu.org/cvs/)
- [Subversion](http://subversion.tigris.org/)
- [Mercurial](http://mercurial.selenic.com/wiki/)
- [Bazaar](http://bazaar.canonical.com/en/)
- [LibreSource](http://dev.libresource.org/)
- [monotone](http://www.monotone.ca/)

If you read the last section carefully, you also noticed that any RCS will need a server to be installed and to keep your code. This is where GitHub, and other web hosting sites come in. While Git is the program, GitHub is a website that offers free servers for anyone to host their projects, as long as they use Git. There are many other web hosts you can choose, but Codecademy only supports GitHub so far. A small list of the most common web hosts for Git can be seen here and remember, if you found anything different, feel free to make a suggestion!

#### Websites that host Git

- [GitHub](https://github.com/)
- [Assembla](https://www.assembla.com/home)
- [Beanstalk](http://beanstalkapp.com/)
- [Bitcucket](https://bitbucket.org/)
- [codebase](http://www.codebasehq.com/)
- [Unfuddle](https://unfuddle.com/)

#### Why Git?
There are many RCSs out there, you can check the list of Git competitors. That list indicates many other RCS that compete in a way or another with Git. 
So, why pick Git out of that list? Is Git the best RCS out there? Well, no. The true answer is complex, mainly because it **depends** on what you actually need, or are willing to learn or even pay for the RCS.
However, Codecademy only supports Git, and it uses the Git account as the only means of communication (instead of allowing us to share an e-mail or something rather more useful). 
This is why I am going to focus mainly on Git. Git has a lot of support out there as well, so hopefully, you'll find this easy.

#### How to install Git?
Installing Git is fairly easy for all major platforms, simply follow this guide for Linux, Mac and Windows:

- http://git-scm.com/book/en/Getting-Started-Installing-Git

#### How to use Git?
Once the previous step is done, you'll have Git installed. Now, Git is mainly a program to be used via command line. If you are familiar with command lines and don't mind using one, then this is an excellent place to start learning:

- [Codeschool tryGit](http://www.codeschool.com/courses/try-git)
- [Atlassian tutorial Git basics](http://www.atlassian.com/git/tutorial/git-basics)
- [Git Immersion](http://gitimmersion.com/)
- [Git Reference](http://gitref.org/)

However, most of you people either are not familiar with command lines, or don't like to use them. Even if you know how to use them, you may prefer a more user friendly way of using the program. If that is the case, then I strongly recommend one of the following GUI programs for using Git:

- [Git official recommendations](http://git-scm.com/downloads/guis)
- [git-gui](https://www.kernel.org/pub/software/scm/git/docs/git-gui.html)
- [Best Git GUI client for windows](http://kylecordes.com/2010/git-gui-client-windows)
- [5 Windows Git Clients To ‘Git’ The Job Done](http://www.makeuseof.com/tag/5-windows-git-clients-git-job/)

At this point, you may have figured out what is Git, and GitHub, but you may still have some doubts. Git is a powerful with many concepts, I advise you to read the following sources:

#### Extra Git tutorials

- [Core Git Concepts](http://www.syntevo.com/smartgithg/documentation.html?page=concepts)
- [Git Book](http://git-scm.com/book)
- [OverAPI Git](http://overapi.com/git/)
- [Become a Programmer, Motherfucker](http://programming-motherfucker.com/become.html#Git)
- [How the Heck Do I Use GitHub?](http://lifehacker.com/5983680/how-the-heck-do-i-use-github)
- [Git and GitHub Version Control Tutorial](http://www.youtube.com/watch?v=mYjZtU1-u9Y)

## Summary
This tutorial is quite extensive, but if you read it carefully you should be able to answer all the questions presented in the introduction. Git is a RCS, in this case a command line program that helps you manage your work with many people. Git needs web hosts to host the code, and one the websites that does that is GitHub. Finally, many people don't like Git command line, so they created many Git GUI programs that you can use. There are many alternatives to Git, I prefer using Mercurial RCS, with BitBucket web host and TortoiseHg as GUI client. What is your favorite set up? Feel free to let us know!

## Sources

- RCS - http://en.wikipedia.org/wiki/Revision_control
- RCS - http://www.techterms.com/definition/version_control
- RCS - http://dictionary.reference.com/browse/version+control
- RCS - http://www.scmwise.com/software-version-control.html
- RCS examples - http://www.smashingmagazine.com/2008/09/18/the-top-7-open-source-version-control-systems/

## Extra Credits

- [Dipesh Bhardwaj](http://www.codecademy.com/dev-dipesh): for the  atlassian tutorial link on Git
- [Jack](http://www.codecademy.com/jack10): for the Pro Git book link
- [SungRim Huh](http://www.codecademy.com/zento): for the Git Immersion link
- [Ksenia Dylova](http://www.codecademy.com/ksenja): for the Git reference link
- [Skinny](http://www.codecademy.com/chipace88921): for the Git video tutorials
- [Aseem Bansal](http://www.codecademy.com/aseembansal): for the life hacker "how the heck do I use Git" guide.