## Prior Requirements
 - [Web Fundamentals Track](http://www.codecademy.com/tracks/web)

----------------

This Guide was created as a direct answer to the question **website design practicing** made by our user [Martin](http://www.codecademy.com/martinmjkeane). If you wish to suggest a theme, feel free to do so in our [voting pool discussion](http://www.codecademy.com/groups/html-projects/discussions/51882c388f6395450000185e)!

----------------

## 1. Introduction

Web Design (not to be confused with web development) is a major part of every website and web application you see in the world. It is responsible by the first impressions a client has when checking out a new shop or a new association, and it can either make the navigation experience a reason to return and use the service, or to forget it into oblivion. 

In this series, you will learn all the rules needed to make a good interface by resorting to materials from the Human-Computer-Interaction course (HCI) from the [FCT][fct] University, so it means that you will be able to apply everything you learn not just to websites, but to computer programs in general.

In this first part you will learn:

1. The differences between Web design and Web development
2. HCI main concepts
3. Basic information about humans and their relation to visual processing
4. The iterative development strategy
5. User and Task analysis
6. How to make sure you are building the website your [stakeholders](http://en.wikipedia.org/wiki/Project_stakeholder) (costumer, project manager) want

So if you are interested in learning how to design a good interface, and if you want to know the secrets of a good design, this guide is just for you.

Each of the previous points were enough for many lectures in the HCI course, and so I will only sum up the majority of what I feel to be important. In the end, access to all the lectures and access to my work is available through links and ZIP files, so if you wish to truly become a good designer, feel free to download them all and remember to give [kudos](http://www.urbandictionary.com/define.php?term=kudos) to [Prof. Teresa](http://www-ctp.di.fct.unl.pt/~tir/), [FCT][fct] and our [WDT group](http://www.codecademy.com/groups/html-projects). 

## 2. Web Design is not Web Development

### 2.1 What is HCI? 

Before we explain what is web design, we must first understand a more general concept: **HCI**. HCI, is defined by *Dix, 1998* as:

> "HCI involves the design, implementation and evaluation of interactive systems in the context of the user’s task."

There are other definitions of HCI:

 - [Human–computer interaction - en.wikipedia.org](http://en.wikipedia.org/wiki/Human%E2%80%93computer_interaction)
 - [HCI - webopedia.com](http://www.webopedia.com/TERM/H/HCI.html)
 - [HCI (human-computer interaction) - searchcio-midmarket.techtarget.com](http://searchcio-midmarket.techtarget.com/definition/HCI)
 - [Human-Computer Interaction (HCI) - techopedia.com](http://www.techopedia.com/definition/3639/human-computer-interaction-hci)

But we will stick with Dix's definition for the guide because it summarizes the main concept of what HCI is. For those of you wishing to become good designers you must know that designing a good interface is a cycle between planning, implementing, testing and then planning again. HCI gives you the methodologies to do just that. 

For now I want you to keep the three stages of HCI in mind:

1. planning or design with user's feedback
2. implementation
3. testing with users

### 2.2 What is web design?

Web design is a sub-category of HCI, specifically oriented to websites. There are many poor definitions of web design and most of them confuse web design with web development, which are two different things. A good definition however is given by [treefrog](http://www.treefrog.ca/what-is-web-design):

> "Design is the process of collecting ideas, and aesthetically arranging and implementing them, guided by certain principles for a specific purpose. Web design is a similar process of creation, with the intention of presenting the content on electronic web pages, which the end-users can access through the internet with the help of a web browser."

Going back to the three main stages of HCI, the web design part clearly fits into stage one - it is the planning and design part where you decide how your website's interface is going to be presented, used, and how it is going to look like.

A web designer's main focus is how a site looks and how the customers interact with it. The web designer designs the look and feel of the website. To summarize:

> "A web designer is a person who manages to ignore his personal likes and dislikes and creates the layout that satisfies and attracts the audience of the future site...
Your project's niche and goals are the factors that all your work should be based on, so don't disregard some basic concepts of marketing, psychology, art and search engine optimization."

-[webdesign](http://www.webdesign.org/)

Web designsers are concerced with things like color schemes, buttons, text placement, layout, etc., and they usually end up producing results like the one below.

![web-designer-work](http://ongoingworlds.files.wordpress.com/2009/10/mockup-game-home.jpg)

### 2.3 What is web development?

Web development is the implementation of the design. Based on our 3 fundamental stages of HCI, web development fits specifically into category 2. Web developers build the prototypes and create the website's back end together with all the information that is not visible to the user such as databases, optimization factors and so on. 

A web developer will take a website design or mock up and actually make a functioning website from it by doing all the coding:

    <html>
      <head></head>
      <body>
        <h1>Ben's Game</h1>
        <p>Lorem ipsum dolor sit amet, consectetuer adipis</p>
         <nav>
         <ul>
            <li>Home</li>
            <li>News</li>
            <li>Games</li>
        </ul>
      </nav>
      </body>
    </html>


The main reason why most people confuse web design with web development it is because most of the time, web designers implement their own websites using frameworks, and other tools available to them, thus effectively also becoming web developers. If you are making a website on your own, then you are both a web designer and a web developer. 

Knowing web design and we development are two different skills that come together, and they are both needed to make good websites come true.

## 3. HCI main concepts

To become a good web designer one must first understand the main HCI concepts and how to apply them into practice. Web design is a specialization, which we will cover in the end. This chapter focuses on interface design concepts, rules and principles. For more information, visit the [IMP1-presentation_usability-intro][IPM-1] file.

### 3.1 HCI three ground rules

Among the many things that you should know as a good interface designer, if there could be only three to obey to, these would make the cut:

1. The users: who is your target audience? Are they young people or old people with trouble in seeing? Are they users who know how to use technology or is it the first time they see it? Design for your target audience!
2. The tasks: which tasks are they going to do? To design a good flow of interaction between your app and the user, you must know exactly their goals and how they usually achieve them, so you can improve it.
3. The context: everything is done within context. A good interface takes advantage of the surrounding context to avoid drawing the user into too much information.

Any good designer will have these three rules in heart. They are so important that they server as a foundation to every other rule and design quality about to be explained in this article. 

### 3.2 HCI design qualities

There are many ways in which one can specify design qualities for a good interface. According to [the first set of slides, IMP-1][IPM-1] there are many factors that contribute to the acceptance of an interface:

![system-acceptability-scheme](https://bitbucket.org/Fl4m3Ph03n1x/codecademy-work/raw/702d35185584e2e77c25ef586228584d3a1ab3c8/IPM/system-acceptability.png)

As you can see, the acceptance of an interface or a system, depends on many factors. However, the most important one is **usability**, and thus this is the one where we are going to focus. For more information you are always free to check the [list of recommended text books for the course][course-bib].

#### 3.2.1 Usability

Usability defines how well the users can use the system's functionality. To achieve this purpose, the usability quality has **five attributes** that can be used to measure its effectiveness:

1. Learnability
    - How easy it is for a new user to start using your system and achieve maximal performance. Systems should be easy to learn in order to a reasonable proficiency level within a short amount of time. This attribute is usually tested by asking a test group of new users to perform a certain task and measuring the time they take to learn how to do it.
2. Efficiency
    - Level of productivity achieved once the user learns how to take advantage of the system's maximal performance. Systems should allow for high levels of efficiency. It is usually measured by measuring the maximum steady amount of time a user takes to perform a set of given tasks.
3. Memorability
    - How easy it is for the user to memorize the usage of the system. Systems should be easy to memorize, so users do not have to learn how to use them again. It is specially important when casual users have to be taken in account. It is measured by giving a set of tasks to a group of standard users and casual users. Then after the test session, ask both groups to explain what* certain commands did and compare the answers.
4. Errors
    - Rate of errors of a system. Systems should have a low rate of errors, and when they do, they should make the situation understandable for the user and help him/her fix it.
5. Satisfaction
    - Level of satisfaction from using a system. It is usualy derived as a consequence from the other attributes. Measurements are usually done by asking the user to rate the system, using [Likert scales](http://en.wikipedia.org/wiki/Likert_scale) or [semantic differential scales](http://en.wikipedia.org/wiki/Semantic_differential).
    
Now that you know all five usability attributes that your system should have it is time to talk about trade-offs. Sometimes, when creating a system, one has to choose between two conflicting attributes, such as learnability and efficiency: which is more important for you? A system easy to learn and thus good for novices, or a system harder to learn but that allows a better efficiency through the use of complex commands? 

As you can see, we are back to HCI ground rules, namely, the first one which is to design accordingly to your target audience. 

Trade-offs should be avoided, but in the real world they are necessary. Therefore, when doing so, specify which attributes are more important accordingly to the target audience and the goals of the project, and strife to accomplish the chosen attributes. 

### 3.3 Going further

In this section we hoovered over the heart of HCI and we presented you the usability principle as the main design quality of HCI. However, there are other ways of categorization used in HCI that were not covered here. Therefore, we recommend the following links, which present additional information on this subject as well as cases of good and bad examples:

- [Usability Principles, Stasko 2007 - cc.gatech.edu](http://www.cc.gatech.edu/~stasko/6750/Talks/03-usabprinc.pdf)
- [Design Rules, Kimani - dis.uniroma1.it](http://www.dis.uniroma1.it/~catarci/HCIslides/HCIDesignRules_April2012.pdf)
- [Using Principles to Support Usability in Interactive Systems - malchevic.com](http://www.malchevic.com/papers/usability.pdf)
- [Usability Goals and Design Principles - cs.umanitoba.ca](http://www.cs.umanitoba.ca/~comp3020/04_Goals.pdf)


As for the [IMP1-presentation_usability-intro][IPM-1] file, it also suggests bibliograpy that you can check as well as a set of good and bad examples of interfaces. It also explains the importance of HCI in every day life as a motivation and it presents alternative HCI categorizations for design principles in the end.

## 4. Human Factor

The human factor is important in every system design and thus it is also target of study. This chapter is highly theoretical, and so I am only going to summarize what I believe you have to know as a designer with as much practical usefulness as possible. For more information, you should check the full set of slides [IPM2-Human-11-12-en][IPM-2].

### 4.1 Human Model Processor

The simplest Human Model Processor has three main points, defining that:

- Humans receive and respond to information through output/input channels (such as eyes, and ears for input, and mouth or hands for output)
- Humans store information in memory (which can be short term or long term memory)
- Humans process and apply the information in several ways

In our specific case of web design, we are interested in the input channels, such as visual sensors like the eyes. Therefore it becomes important to know this sensors well enough in order to explore their strengths and weasknesses in our advantage.

You should keep in mind that this is a very basic human model, but for our guide it will do. For more information about human models and interactions you can see:

- [Human processor model - en.wikipedia.org](http://en.wikipedia.org/wiki/Human_processor_model)
- [Lecture 3: Human Capabilities - groups.csail.mit.edu](http://groups.csail.mit.edu/graphics/classes/6.893/F03/lectures/L3.pdf)
- [HCI Foundations: Human - users.soe.ucsc.edu](http://users.soe.ucsc.edu/~srikur/files/lect2.pdf)

### 4.2 Input Sensors - the eyes

Here, because our focus is web design, we will take a look on the visual sensors (eyes) and how their properties and differences can be used to make good decisions when building interfaces. 

The human eye is a complex mechanism that receives light and then transforms that light into electrical signals that can be processed and interpreted by our brain. 

The human eye has several types of specialized cells, but for the web designer the area known as the [retina](http://hyperphysics.phy-astr.gsu.edu/hbase/vision/retina.html) is the most important. The retina contains 2 types of photoreceptors: 

- Rods: highly sensitive to light, allowing us to see under a low level of illumination (dominate peripheral vision); 
- Cones: allowing colour vision (sensitive to different wavelength of light).

Related to these two areas of the human eye, there are three main concepts one should know:

- Size, depth and context
- Brightness
- Colour

#### 4.2.1 Size, depth and context

Perceiving size and depth is fundamental in any interface and it is linked to two important concepts:

- visual acuity, which is the ability of an individual to see fine details
- context, the surroundings of the target that we use to give it meaning

Visual acuity is important on its own because without it the user cannot see the image and does cannot infer anything from it. In the case of context, it can be related to distances (placing an image in front of another usually makes the user perceive the background image as being farther away) or to logic. 

Optical illusions usually exploit deficiencies in the context, by either taking advantage of missing information or given assumptions. Context is extremely important to solve ambiguities and as a designer you should leave out as many assumptions as possible in order to have a complete context. 

As an example, is the next image a letter or a number? Which letter or number could it be?

![no-context](https://bitbucket.org/Fl4m3Ph03n1x/codecademy-work/raw/702d35185584e2e77c25ef586228584d3a1ab3c8/IPM/no-context.png)

What about now?

![context](https://bitbucket.org/Fl4m3Ph03n1x/codecademy-work/raw/702d35185584e2e77c25ef586228584d3a1ab3c8/IPM/context.png)

As you can see, the image can either be a letter or a number **depending on the context**. For a list of more optical illusions, you can visit the [Wikipedia's List](http://en.wikipedia.org/wiki/List_of_optical_illusions).

This sub-section is not here by accident. It goes back to one of your thumb-rules for HCI, which is rule number 3, the context. Thus, **as a designer, never forget to make the context clear for the user**.

#### 4.2.2 Brightness

Brightness is defined in [thefreedictionary](http://www.thefreedictionary.com/brightness) as:

> "The state or quality of being bright."

Brightness is subjective to the sensitivity of each individual's rods and it is affected by the **luminescence** of an object, which is the ability of an object to emit light. Therefore, objects that have a high level of luminescence (like stars) are considered to be very bright.

Because this is such a subjective aspect of each person's rods, it is then important for web designers to make the best use of it. This is where another term comes in: **contrast**. Contrast is the difference between the luminescence of an object, and the luminescence of its background. 

Great differences in contrast make objects easier to see without requiring as much effort from the user's rods. Consequently, this helps avoiding side effects resulting from long exposure to objects with high levels of brightness, like [visual fatigue (Asthenopia)](http://www.deir.qld.gov.au/workplace/law/contact-centres/visual-fatigue/index.htm#.Urnn2bRvWDQ) or even [flash brightness](http://en.wikipedia.org/wiki/Flash_blindness). 

Therefore, the practical lesson to take from here: use contrast to make objects easier to see while not forcing the eyes of the user too much. 
Objects with a high level of luminescence may be easier to see, but the user's eyes will be fatigued a lot faster in exchange. **Contrast is your friend.**

#### 4.2.3 Colour

There are many [color models](http://en.wikipedia.org/wiki/Color_model) one can use to specify and create color. One of the most widely used, is the RGB color model, where each color is composed by a mixture of red, green and blue. 

The cones in our retina use this model. To be more specific, there are three types of cones in our retina:

- S, detect blue
- M, detect green
- L, detect red

However, these three types of cones are not present in equal quantities in our eyes. In fact, only 3%-4% of the cone cells in our eyes and of type S (detect blue), thus meaning that blue acuity is lower when compared to green and red acuity.

Therefore, the practical lesson to take from here: **never use blue in your website for small details**, because they will be harder for the user to see. 

Another very important thing to be careful about when using colors is to avoid [oversaturation](http://www.thefreedictionary.com/Oversaturate). Oversaturation occurs when is exposed for long periods of time to highly saturated and vivid strong colors, such as light green and red. Such colors will not only cause visual fatigue, but also optical illusions such as the [afterimage illusion](http://en.wikipedia.org/wiki/Afterimage_effect), which should be avoided at all costs.

A last conclusion to take from here, is to avoid strong colors as backgrounds in order to prevent oversaturation.

The retina is a complex machine, and the differences between cones do not end here. If you wish to learn more about this matter, feel free to read the following documentation:

- [Wiki Cone cells - en.wikipedia.org](http://en.wikipedia.org/wiki/Cone_cell)
- [Rods & Cones - cis.rit.edu](http://www.cis.rit.edu/people/faculty/montag/vandplite/pages/chap_9/ch9p1.html)
- [Rods and Cones - hyperphysics.phy-astr.gsu.edu](http://hyperphysics.phy-astr.gsu.edu/hbase/vision/rodcone.html)


### 4.3 Going Further

Because this is just a simple guide meant to be as practical as possible for web designers, the other sections of the human body such as the auditive, movement and memory systems were not covered. 

The chapter about human audio describes the basics of the human hearing system and the fact that you can use it as a mechanism for feedback. The section about movement introduces you to [Fitt's Law](http://en.wikipedia.org/wiki/Fitts%27s_law) and its consequences, such as why designing interfaces with bigger buttons is better. Last but not least, the human memory section will teach how you the types of memories we have as well as their limitations, and what that means when making interfaces that require long sequences of steps to achieve goals. The slides also cover other aspects of human interaction such as thinking and emotions, but to a less level of detail and importance.

## 5. Development strategies

There are many ways to develop a software and as a web designer and/or developer you should be familiar with at least a few of them, because in the end of the day, developing a website is still developing software, and there is much to gain from having a structured development process. This chapter is based on the file [IPM3-Iterative-Design-User-TaskAnalysis][IPM-3], remember to check it out.

### 5.1 What is a development strategy?

Wikipedia defines a [Software Development Strategy (SDS)](http://en.wikipedia.org/wiki/Software_development_process) as: 

> " A software development process (SDP), also known as a software development life-cycle (SDLC), is a structure imposed on the development of a software product."

For the purpose of this article SDS, SDP  and SDLC all refer to the same notion: a structured way of developing software. Such structure is needed in order to avoid releasing products that your stakeholder does not want, fix mistakes on the go, and to have the necessary feedback to develop a good work in the end. 

### 5.2 Iterative SDS

There are many SDS's, [IPM3-Iterative-Design-User-TaskAnalysis][IPM-3] presents two well known strategies:

- [Waterfall Model - en.wikipedia.org](http://en.wikipedia.org/wiki/Waterfall_model)
- [Iterative Model - en.wikipedia.org](http://en.wikipedia.org/wiki/Iterative_and_incremental_development)

Those slides explain the main reasons why the waterfall model should not be used when developing interfaces, and proposes the Iterative model as a solution. The answer however, is not so simple. The truth is that there is quite a considerable number of SDSs that one can use, depending on the project and on the situation, and any software engineer is required to know them:

- [Software Development Strategies and Life-Cycle Models - informit.com](http://www.informit.com/articles/article.aspx?p=605374&seqNum=2)
- [Software development process - en.wikipedia.org](http://en.wikipedia.org/wiki/Software_development_process)
- [Software Life Cycle Models - levela.com](http://www.levela.com/software_life_cycles_swdoc.htm)

I strongly recommend you to give a brief overview of their strengths and weaknesses as they will make you a better overall professional. However, since the purpose of this guide is to teach you some basic rules and guidelines of good web design and development and not to make you a software engineer, those SDSs will not be covered.

As a web designer/developer, there is however one specific SDS that you must be familiar with, the **Iterative Model** centered in the user.

For the web designer/developer, the Iterative Model can be simply summarized by the following image:

![iterative-model-graph-detailed](http://www.onestoptesting.com/images/iterativemodel.jpg)

This simple image is very rude but it explains the heart of this SDS. As you can see, each iteration is composed by four basic steps:

1. Requirements or Planning: gather all the information from the clients, their tasks and other forms of feedback including step 4.
2. Design: create a design based on the information received from step 1.
3. Implementation: implement the new interface.
4. Evaluation: ask a group of users to evaluate how good your interface is and collect opinions and feedback from them. Then release v1 of your interface and use the collected feedback to go back to point 1.

Using the Iterative Model SDS has several advantages:

- In general, the iterative development model allows for early adjustments to the product during development.
- Serious misunderstandings are made evident early in the lifecycle, when it's possible to react to them.
- It enables and encourages user feedback, so as to elicit the system's real requirements.
- The workload of the team, especially the testing team, is spread out more evenly throughout the lifecycle.
- The system grows by adding new functionalities in the implementation part of all iterations.
- **Stakeholders** (your bosses) in the project can be given concrete evidence of the project's status throughout the lifecycle.
- In iterative model less time is spent on documenting and more time is given for designing.
- A good interface following this model goes through several iterations and several versions. This way, the last release will be strong because it was evaluated and remade several times based on user's feedback. 

However, there are also some disadvantages that you should be aware of:

- Each phase of an iteration is rigid with no overlaps.
- The users must be involved in the life cycle. If they are not, then there is a bigger chance they will be reluctant to using your final version.
- Users tend to make more and more requests as they are involved in the project, and this can in turn result in delayed deadlines and budget inconsistencies.
- There is no clear end, there is no last version as because there is usually always something that can be improved. To counter this one must specify static goals and fight towards them, but even then the goals can change.

So when developing your interface this is what you should have in mind. Always remember to have the users involved in the life-cycle of your application and remember: iterative development means several iterations (versions), not just one iteration - if you do just one iteration, then you are not doing using the Iterative SDS correctly. 

### 5.3 Going Further

I have covered only the tip of the iceberg about the iterative SDS. There is much more I could have said, so here are a few more good articles and books that you can check. Knowing this SDS will help you greatly even if you are not a web developer, so I strongly recommend you read at least a few of the links I suggest:

- [Iterative Model - onestoptesting.com](http://www.onestoptesting.com/sdlc-models/iterative-model.asp)
- [What is Iterative model- advantages, disadvantages and when to use it? - istqbexamcertification.com](http://istqbexamcertification.com/what-is-iterative-model-advantages-disadvantages-and-when-to-use-it/)
- [What is Iterative model- advantages, disadvantages and when to use it? - wiki.answers.com](http://wiki.answers.com/Q/Advantage_and_disadvantage_of_iterative_development#q99838468/page/13)
- [Incremental build model - en.wikipedia.org](http://en.wikipedia.org/wiki/Incremental_build_model)
- [ITERATIVE & EVOLUTIONARY - catalogue.pearsoned.co.uk](http://catalogue.pearsoned.co.uk/assets/hip/gb/hip_gb_pearsonhighered/samplechapter/0131111558.pdf)
- [Agile and Iterative Development: A Manager's Guide - books.google.pt](http://books.google.pt/books?id=76rnV5Exs50C&pg=PA21&lpg=PA21&dq=iterative+model+common+mistakes&source=bl&ots=o8-6RrJSP-&sig=JgVbOpgnYNNFoBPw5MuLuuOTeWk&hl=pt-PT&sa=X&ei=Oq-8UvvBC-ag7AbfgoCADQ&ved=0CF8Q6AEwBQ#v=onepage&q=iterative%20model%20common%20mistakes&f=false)

## 6. User and task analysis

In the previous chapter we presented you a SDS to develop software centered on users. However, when developing any kind of software, websites included, you have to know your target audience. This means you have to know what kind of people will use your system, and how they will exactly use it. Therefore, it is important to analyze the tasks your users will perform in order to make sure they are as intuitive and as easy as possible. User and task analysis plays a big role on the requirements/planning phase of the iterative SDS due to all the feedback that it can provide, and so it is important that you at least know the basics of this area. This information is also explained in detail in the file [IPM3-Iterative-Design-User-TaskAnalysis][IPM-3].

The first steps of a user centered design are to know:

1. User analysis: Who are the users?
2. Task analysis: What does the user need to do?

### 6.1 User analysis

User analysis is usually done by collecting data about the demographic group of users that you are interested in. This usually helps you identify certain characteristics, such as:

- age, gender, ethnicity
- education
- physical abilities
- general computer experience
– domain experience
– application experience
– work environment and social context
– communication patterns

For example, if you are building a website for people with age between 15-20, that all have a good general education, experience with computers and no major physical disabilities then you are allowed to build a website that is more flashy, displays information with a slick design and has several connections to social networks. If however you are building a website for elderly people, that are color blind and have a difficult time adapting to new technologies, than you have to make a simple design, bigger buttons and you have to pay attention to the colors and their combinations.

User analysis is always the first step any good designer takes, and that happens for a reason. After all, you do not want to be building a website for the wrong audience. This article from smashing magazine does an overall good evaluation of portfolios by evaluating their usability:

- [Can User Experience Be Beautiful? An Analysis Of Navigation In Portfolio Websites](http://www.smashingmagazine.com/2012/03/26/an-analysis-navigation-portfolio-websites/)

The first example, shows how important knowing your users and what they like is. The first portfolio (that is now under reconstruction) gave the strong impression that the artist required the user to use a technique called *Mine-sweeping!* in order to navigate the website. This technique is loved by children, but hated by teenagers and adults. Who do you think will contact the artist for a job? Adults or children?

For an acceptable list of possible categories for users, you can check the [WAI section of w3.org](http://www.w3.org/WAI/redesign/users). This is only a suggestion though, you are free to define your own.

### 6.2 Task analysis

If the first task of any good web designer is User analysis, then the second is task analysis. Now that you know your users, it is time for you to know why they do what they do, and how they expect to do it. This will allow you to better understand how you can design a good interface that meets their expectations. Simply put, task analysis is the study of how people perform their tasks/jobs:

- What do users do?
- Why do they do it?
- How do they do it?
- What do they have to know?
- What tools do they use?
- How can your interface improve the way the task is done?

Task analysis can be done in three steps:

1. Identify the goal of the activity
2. Identify any pre-conditions that are required to achieve the goal
3. Identify sub-tasks that need to be done in order to achieve the goal

There are many ways in which you can specify these three steps, in HCI we usually use diagrams to explain how a user can perform a task. In my reports I used a type of diagram called Hierarchical Task Analysis (HTA) to describe every step that the user had to do for every possible action in our website. HTA diagrams are usually simple, but can become long and tedious to make, as in the example below:

![hta-making-tea](https://bitbucket.org/Fl4m3Ph03n1x/codecademy-work/raw/702d35185584e2e77c25ef586228584d3a1ab3c8/IPM/HTA.png)

If you are thinking this is overkill for a web designer, you are probably right. In fact, very few people in the web industry actually do them. This is usually useful when you are making a different application from what is usually done, or when you are trying to figure out how actions in the real world should be mapped into a web application or website. 

### 6.3 Going further

In this chapter we covered user analysis, which should be a must in every project, and task analysis. Task analysis usually helps you organize and structure the actions the user has to go through because you are forced to think about them in advance, during the planning stage before you can design the interface. Although seen as a good practice, it can be time consuming and is usually skipped, specially if you are in a company working for a big project that requires fast iterations over the iterative SDS. For this reason, we decided to not cover it in detail.

Still, Task analysis is considered by many an important step in design, and if you have the time, you should invest in it, as it will result in a better understanding of the user's activities and therefore in a better interface for your webpage. More information about Task analysis can be found in the following links:

- [Task analysis - en.wikipedia.org](http://en.wikipedia.org/wiki/Task_analysis)
- [TASK ANALYSIS TECHNIQUES - PDF paper - cwsvt.com](http://www.cwsvt.com/Conference/Functional%20Assessment/Task%20Analysis%20Techniques.pdf)
- [Task analysis - PDF document - idemployee.id.tue.nl](http://www.idemployee.id.tue.nl/g.w.m.rauterberg/lecturenotes/UFTtask-analysis.pdf)
- [TASK ANALYSIS - behavioradvisor.com](http://www.behavioradvisor.com/TaskAnalysis.html)
- [Task analysis - usabilitynet.org](http://www.usabilitynet.org/tools/taskanalysis.htm)

The pdf file explores both user and task analysis in greater detail as well. It introduces you to new ways of analyzing tasks, such as task descriptive hierarquies (TDH), knowledge representation grammars (KRG), entity-relationship models, etc, and is filled with examples that you can explore as well.

## 7. Build what your stakeholder wants

In the previous section you were presented with user and task analysis. This matters because in the end of the day, you are making a website for your stakeholders and you need them to like the work you are doing. In this section, we introduce you to website planning. Here you will learn what questions you have to ask to ensure that you are making the product the stakeholders expect. 

### 7.1 Website Goals and purpose

Figuring out what the focus of the website will be should be your first step of planning your website. What will your website be used for? 

- Web store
- Social network
- Entertainment or gaming website
- Portfolio
- Simple branding site to show contacts 
- Search Engine Optimized (SEO) 
- etc.

There are a lot of types of websites, and they are all done differently, many times using different technologies as well. For example, building a SEO website that searches through private data requires a heavy backend with a customized database and is therefore more time consuming and expensive as well. Knowing what type of website you want also helps you recognize important features in other websites that have the same purpose or type. **In doubt, just ask it.**

As an additional note, it is important to know that the categorization of a *type* of website depends on a lot of criteria. Here you were presented with some basic types based on the criteria of content, but there are other forms of categorization. For additional information, we recommend:

- [Website - en.wikipedia.org](http://en.wikipedia.org/wiki/Website)
- [What are the Various Types of Websites? - xislegraphix.com](http://www.xislegraphix.com/website-types.html)
- [Types of web sites - a categorization based on content - webdevelopersnotes.com](http://www.webdevelopersnotes.com/basics/types_of_websites.php)
- [Types of websites - mediatopia.co.uk](http://www.mediatopia.co.uk/types-of-websites)

### 7.2 Website specific features and perks

There is a moment in every website where you will need to know exactly how to display and collect the information that is given and that you have collected. Depending on the website, you have to figure out your specifications:

- Will the website have content that the user can edit?
- Will the user be able to submit forms?
- A shopping cart with access to PayPal or MBnet?
- A password protected section of the website (such as user account)
- Show images in a slider
- Share, upload and download videos
- etc.

After knowing what you need, you have to invest some time in searching for solution that already exist. For example, if you want to make a portfolio with an image slider, you can use our [How to make image sliders using Flex Slider ](http://www.codecademy.com/groups/html-projects/discussions/51882c70302afb437d0001a2). If you want a website with a responsive interface, you can check out our [Twitter Bootstrap - Websites for all Screens, Devices, Browsers and more!](http://www.codecademy.com/groups/html-projects/discussions/51aa686665ce54dbae0017a8) tutorial. For each problem there are a lot of technologies that you can use, and you should always search for them in advance. 

Once you know what technologies you can use to solve your problems, you have to learn them and play with their strengths and limitations. For example, Flex slider struggles with images of different sizes but it is fast, Twitter Bootstrap is complex and rich in features and has a great community, but it will take you some time to master. Knowing this will allow you to better plan the design of your website. **Always know the tools you use, or else you risk planning a website that cannot be built**.

When searching for tools and options, search engines like [Google](www.google.com) are an excellent choice, but you can expand your search by trying others as well:

- [The 10 Best Search Engines of 2014 - netforbeginners.about.com](http://netforbeginners.about.com/od/navigatingthenet/tp/top_10_search_engines_for_beginners.htm)
- [Top 15 Most Popular Search Engines | January 2014 - ebizmba.com](http://www.ebizmba.com/articles/search-engines)
- [List of search engines - en.wikipedia.org](http://en.wikipedia.org/wiki/List_of_search_engines)

Even though search engines are very good, there are also other options, such as forums and communities. For this effect we recommend our [Alternatives to Codecademy](http://www.codecademy.com/groups/html-projects/discussions/52363231f10c60819600030a) guide, which will introduce you to a whole new world of web development possibilities. Enjoy! 

### 7.3 Website Look and feel

Ask your stakeholders the colors and feel that they like. Present them with examples of color pallets that you think are good or with examples of websites that you think they will enjoy. Sometimes the colors that you have to use are already defined by the company or are imposed by a logo. In sum, find a style / look that meets your website's and your stakeholder's requirements:

- Will the website have a color scheme or a certain layout that it should follow?
- What kind of buttons will be used?
- Is there a logo I have to use? What are the dominant colors of the logo? 
- Will I require user sign-in? Where should the user sign-in be placed?

Here are some common pallet suggestions for your website. If you are using a common framework, like Bootstrap, then you can also search the community for icon styles, and more complex templates, but that really depends on the tools you use:

- [10 Beautiful Website Color Palettes That Increase Engagement - blog.crazyegg.com](http://blog.crazyegg.com/2012/07/11/website-color-palettes/)
- [50 Beautiful Color Palettes for Your Next Web Project - dtelepathy.com](http://www.dtelepathy.com/blog/inspiration/beautiful-color-palettes-for-your-next-web-project)
- [Color Scheme Designer - colorschemedesigner.com](http://colorschemedesigner.com/)
- [Color Combinations and Color Schemes - colorcombos.com](http://www.colorcombos.com/)

### 7.4 Prepare for the future, or go [Back to the Future](http://www.imdb.com/title/tt0088763/)

Ask your stakeholder what are his future goals and prepare your website to be updated accordingly to his expectations. When companies and businesses grow, their websites must also grow. Avoid the need to re-design and re-create a website from scratch just because you did not plan ahead.

Making a future-friendly website is important, not just for your stakeholder, but also for your career. **Good work immortalizes the worker**. Therefore we recommend you to take a look on the following articles about making a future-friendly website, and hopefully, a future-friendly web:

- [Building a Responsive, Future-Friendly Web for Everyone - webmonkey.com](http://www.webmonkey.com/2012/01/building-a-responsive-future-friendly-web-for-everyone/)
- [Progressive Enhancement - A Technique For Building Future Friendly Websites - responsivedesign.ca](http://responsivedesign.ca/blog/progressive-enhancement-a-technique-for-building-future-friendly-websites)
- [For a future-friendly web - alistapart.com](http://alistapart.com/article/for-a-future-friendly-web)
- [For a future-friendly web - slideshare.net](http://www.slideshare.net/bradfrostweb/for-a-futurefriendly-web)

### 7.5 Going further

Now that you know what to ask to your stakeholders, you are ready for the next part of this tutorial series, which will explain prototyping, design rules and more. For now however, we simply recommend the following article:

- [How To Properly Plan A New Website - webduckdesigns.com](https://www.webduckdesigns.com/page/swebsite-resources/plan-website.html)

## 8. Conclusion

Overall, this first part is more important for those of you who wish not just to design your websites, but to implement them too. Having in mind this is what happens most of the time you should now have some basic notions on how to get started.

First we learned that web design focuses on the aspect and usability of the website, while web development focuses on the tools that you have to use to make it come true. Then we delved into HCI main concepts - the users, the goals, and the tasks - and presented you with the most sacred principle of HCI: **usability**. Once that was out of the way, we understood how human eyes work and learned how to take advantage of its strengths and limitations. For those of you more into web development, we also covered the iterative software development strategy and then we jumped to user and task analysis, but only for a brief moment. Last but not least, we concluded with a set of questions and actions that you should always take in order to ensure that you are making the work that you are getting payed for.

The next part of the tutorial will cover the main aspect of design. We will introduce you to the interface development cycle, and present you with sets of rules designed specifically to design good interfaces and good websites, while not forgetting rules to evaluate them as well! So stick around to learn more !

## 9. Lessons, and reports

This whole guide would not have been possible without the PDF files and the hard work done by the people invested in the HCI course. Still, this guide only covers a small section of everything you can learn. Therefore, you can download the ZIP with all the lessons for free here:

- [IPM-Lessons](https://bitbucket.org/Fl4m3Ph03n1x/codecademy-work/src/702d35185584e2e77c25ef586228584d3a1ab3c8/IPM.zip?at=master)

The reports that I made during the HCI course are also available to anyone online. Special thanks to my good German friend Marco Rüth for staying awake with me many long nights and helping me finish the course. You can check them all in the following links:

 - [Stage-1](https://docs.google.com/document/d/1h0GNGf-OtMY5Wzf71iAt9ZrfBvD4KmTj_mBfoYItpLE/edit)
 - [Stage-2](https://docs.google.com/document/d/1fKbFIwSt-WckxX3seVMWTMMVWxxCDk_rEipZ0Gza8to/edit)
 - [Stage-3](https://docs.google.com/document/d/11GUcXTeJNQ2JGXvTI972SyfdNjmvAYFbAk0ySzKCvp4/edit#heading=h.etmnonk7iw9l)
 - [Stage-4](https://docs.google.com/document/d/1FWguE-RR5CamZB2isjX3b1nNaOtPOwq5kGGDpCdy1PA/edit)
 - [Stage-5](https://docs.google.com/document/d/1H7yvZl4sTXNdz9ki0p80AA3umASVyylgPWf-iwTc7Tg/edit)
 - [Problems-table-5](https://docs.google.com/spreadsheet/ccc?key=0AuUP5lxiQ9AodDFhZzZPdzNDX0RsU0FlNjgxMTNMNHc&usp=drive_web#gid=0)
 - [Stage-6](https://docs.google.com/document/d/1T9LaQ5S801u57houpixSsy5Db-NMLXpOwqbWTsrcO-c/edit)

## 10. Special Thanks

### 10.1 People

- [Pedro Martins](http://www.codecademy.com/fl4m3ph03n1x) - the author
- [WaffleGnome](http://www.codecademy.com/wafflegnome) - co-author, original creator of the discussion
- [Chris Meyer](http://www.codecademy.com/bytewhiz68766) - for support and feedback 

### 10.2 Tools and projects

- [Online Spell check, Grammar, and Thesaurus checking](http://www.spellchecker.net/spellcheck/) - for being an awesome, online, free spellchecker

  [fct]: http://www.fct.unl.pt/
  [IPM-1]: https://bitbucket.org/Fl4m3Ph03n1x/codecademy-work/src/d574a6ed616cd97033dedabc07df406fac5be060/interface-design-basics/IPM/IMP1-presentation-usability-intro.pdf?at=master
  [IPM-2]: https://bitbucket.org/Fl4m3Ph03n1x/codecademy-work/src/d574a6ed616cd97033dedabc07df406fac5be060/interface-design-basics/IPM/IPM2-Human-11-12-en.pdf?at=master
  [IPM-3]: https://bitbucket.org/Fl4m3Ph03n1x/codecademy-work/src/d574a6ed616cd97033dedabc07df406fac5be060/interface-design-basics/IPM/IPM3-Iterative-Design-User-TaskAnalysis.pdf?at=master
  [IPM-4]: https://bitbucket.org/Fl4m3Ph03n1x/codecademy-work/src/d574a6ed616cd97033dedabc07df406fac5be060/interface-design-basics/IPM/IPM4-Sketching-Prototyping11-12-en-clip.pdf?at=master
  [IPM-5]: https://bitbucket.org/Fl4m3Ph03n1x/codecademy-work/src/d574a6ed616cd97033dedabc07df406fac5be060/interface-design-basics/IPM/IPM5-Interface-Analisys-Conceptual-Models11-12-en.pdf?at=master
  [IPM-6]: https://bitbucket.org/Fl4m3Ph03n1x/codecademy-work/src/d574a6ed616cd97033dedabc07df406fac5be060/interface-design-basics/IPM/IPM6-DesignRules-InfoVisual-colors-GraphicDesign11-12-en-clip.pdf?at=master
  [IPM-7]: https://bitbucket.org/Fl4m3Ph03n1x/codecademy-work/src/d574a6ed616cd97033dedabc07df406fac5be060/interface-design-basics/IPM/IPM7-Icon-Dialog-Implementation11-12-en.pdf?at=master
  [IPM-8]: https://bitbucket.org/Fl4m3Ph03n1x/codecademy-work/src/d574a6ed616cd97033dedabc07df406fac5be060/interface-design-basics/IPM/IPM8-GOMS-Evaluation-11-12-en-clip.pdf?at=master
  [IPM-9]: https://bitbucket.org/Fl4m3Ph03n1x/codecademy-work/src/d574a6ed616cd97033dedabc07df406fac5be060/interface-design-basics/IPM/IPM9-InteractionMachine11-12-en-clip.pdf?at=master
  [IPM-10]: https://bitbucket.org/Fl4m3Ph03n1x/codecademy-work/src/d574a6ed616cd97033dedabc07df406fac5be060/interface-design-basics/IPM/IPM10-Paradigms-FuturePersp-links11-12-en.pdf?at=master
  [course-bib]: http://ctp.di.fct.unl.pt/mei/ipm/page3/page3.html
