#### Here is the place for wishes - not bugs or complaints. 
Think about things you'd like to see added to or changed at Codecademy.

**NOTE:** This discussion will be for wishes that only apply to Mods and so don't belong on the [public Wish List](#). If your wish belongs on the public list, please don't add it here.  The public list will go live after we do some test driving here. I'm using your reaction here to adjust my strategy there.

This initial post will be for maintaining a list of wishes that have gathered +3 votes.

**If your wish is already here in this initial post**, DO NOT start a new response for it. Feel free to follow the link and add your +1 to the already existing response.

**If your wish is not here**, browse through the subsequent responses to see if your wish has been suggested by someone else. 

- **If you find it** then just add a new comment to it and place your vote by making the first two characters of your comment **+1** so that it will be easy to see. After that you may add any additional comments you feel are necessary.
- **If you do not find it** then new wishes should be posted as new responses. ONE wish per response so we can discuss and vote on it.

In order to avoid a big mess, please stay on topic and keep your comments attached to the right discussion. Out of place discussions and comments will be removed to preserve our sanity. Any +1 votes left in places other than as described above will be ignored. Anything that qualifies as a Site Bug should be written up as a new issue in our [GitHub repo][1].

##### Other lists of wishes we may want to sort through, posted here to at least keep track of their existence. Please add any others as you find them.:
Giacomo's [*"The Q&A Forum of my dreams"*](http://www.codecademy.com/groups/codecademy-mods/discussions/51702dd35006c746be001180).

-------

#### Wishes with +3 or more will be listed here:

[Groups - Ability to mark discussions as closed which would preventing further reponses/comments](http://www.codecademy.com/groups/codecademy-mods/discussions/5329ed6c9c4e9d147c00324f#response-5330698b9c4e9d078e00089f) 
[Groups - Ability to move discussions to a more relevant group](http://www.codecademy.com/groups/codecademy-mods/discussions/5329ed6c9c4e9d147c00324f#response-5330a220282ae303670007d0)
[Groups - Add a flag system](http://www.codecademy.com/groups/codecademy-mods/discussions/5329ed6c9c4e9d147c00324f#response-5336f0029c4e9dd03e003319)
[Groups - Give moderator abilities to all mods in all groups](http://www.codecademy.com/groups/codecademy-mods/discussions/5329ed6c9c4e9d147c00324f#response-532a0a437c82caa25f00388a
)

[Mod Tools page - Fix links that give a Error 503 backend read error](http://www.codecademy.com/groups/codecademy-mods/discussions/5329ed6c9c4e9d147c00324f#response-53306568631fe9b28300086e)
[Mod Tools page - Improve flag system](http://www.codecademy.com/groups/codecademy-mods/discussions/5329ed6c9c4e9d147c00324f#response-5336f0029c4e9dd03e003319)
[Mod Tools page - Access to Change Log](http://www.codecademy.com/groups/codecademy-mods/discussions/5329ed6c9c4e9d147c00324f#response-5339c93a52f8637a0300a121)

[Q&A - Ability to move questions to a more relevant forum](http://www.codecademy.com/groups/codecademy-mods/discussions/5329ed6c9c4e9d147c00324f#response-5330a220282ae303670007d0)
[Q&A - Improve flag system](http://www.codecademy.com/groups/codecademy-mods/discussions/5329ed6c9c4e9d147c00324f#response-5336f0029c4e9dd03e003319)

  [1]: https://github.com/RyzacInc/help.codecademy.com


Ok so this is a pretty big wish and it would take quite some time to be implemented but I will put it out here anyway. What I'm proposing is a new way to deal with bugs and instructional errors within Codecademy exercises. The idea behind it is to have a way of users being able get to us more directly and to also have a central place for us all to see what is going on. To put it simply I want a report center, you commonly get them in forums.

So the life cycle of a report:

First a user who spots a bug or instructional error and clicks a link to make a report regarding the current exercise they are doing, I have included some demo simple interfaces:

![report issue link][1]

Then, a modal dialog will come up listing open reports for this exercise, the user should continue only if their issue is not there.

![alt text][2]

If the user continues, they can briefly but concisely explain the issue with the exercise and the report formalities are explained.

![form][3]

After they have submitted their report, they will get a simple pop up that fades away:

![popup][4]

That's it for the regular user end, now for the moderator end. There should be a unified page that all moderators and admins can access. It should have sections such as **Open Reports** and **Closed Reports** and the ability to move reports between the two sections.

Within each section should be a tabular list of reports with information such as the **course**, **section**, **exercise** and **creation time**

For each entry there is a button **View Report** which allows you to read the **description** of the issue that the user who made the report wrote and a **link to the exercise** so moderators can test and confirm it is actually an issue.

On this page there will also be buttons, such as **Close report** or if you were looking in the closed section to bring back an issue from before then **Open report**.

When a report is moved to the closed reports section, it gains an extra attribute **Closed by \<mod name\>**. Then if a moderator wished to reopen the issue it loses that attribute and gains the attribute **Reopened by \<mod name\>** and being able to input a reason of reopening would be awesome too.

Unfortunately, I haven't had time to create a mockup of the interface for this part, but I'm sure you can all use your imagination, or look at some example of report centers :)

Anyway what are people's thoughts on this?


  [1]: http://puu.sh/7FekS.png
  [2]: http://puu.sh/7Flk9.png
  [3]: http://puu.sh/7Fene.png
  [4]: http://puu.sh/7FfLI.png


**[added to Mod's list]** Flags. 

 1. We need a flag system in Q&A and Groups
 2. We need a way to be alerted to new flags
 3. We need to be able to remove flags

We need flags to work as an easy way for users to alert us to offensive posts. Several times I've stumbled across a message in a thread along the lines of "Hey mods, this other post is offensive". Generally the message is weeks/months old.

The trouble now is that they can flag all they want in Q&A but we don't get alerted. I have on occasion used our Mod tools to go and trawl through the list of flagged posts but many of those flagged posts don't deserve to be flagged. We can't unflag them so we can't get them off the list.