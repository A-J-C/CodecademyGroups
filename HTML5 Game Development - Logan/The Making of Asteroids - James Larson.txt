I see lots of posts from Codecademy members wanting to make their own video games. Such a goal is a worthy challenge indeed! Producing a fresh, addictive, well implemented game is a synergy of many disciplines including: programming, graphics, physics, sound, music, human factors, and raw creativity.

If all that talent is present in a single individual, he/she is a rarity, indeed.

I'll confess right here right now: I lack several of those particular talents. My strength lies in programming. So I am sort of dependent on others for the balance of those capabilities. 

What I want to do here is help teach those of you who might want to try your hand at creating a video game the basics of the programming involved. I can teach about sprites, collision, variable discipline, game state maintenance, managing dynamic objects, code organization, and more. I will attempt to share the years of experience I've accumulated.  

For the sake of simplicity, we'll skip the music and sound. If you'd like to get an idea of where we're going, [click here](http://binarytutor.x10.mx/HTML5-Asteroids/Game.html)

We'll go step by step, adding features as we go. Start simple - the ship on the screen, then add motion, control, asteroids, bullets, aliens, alien lasers, scoring, and lives. Step by step, you will see how to build a robust, working game. You are welcome to modify the design as you go, to produce your own custom version. 

Hang on to your hats! Let the fun begin!

**Credits:**
![Alex P avatar](http://s3.amazonaws.com/codecademy-production/profile_thumbnail/52f4fe90282ae30e2500001d_448554745.png)
The original code and graphics in this game were done by [Alex P](http://www.codecademy.com/users/apeggs2000)


# Asteroids: Lesson 1
**Foundations**
Like any artifact, a good video game requires a solid foundation. There are many to choose from these days, HTML5 growing more popular as folks work with it and learn it. This asteroids game tutorial will be based on HTML5, and a cute little library called "simpleGame.js." There is a lot of cool stuff in that library that will allow us to move images along the screen, rotate them, control them, plus much more.

But enough introduction. Let's get started!

First, we should choose a place to host our game program. I like [jsBin](http://jsBin.com) as it is easy to use and convenient. If you go ahead and click on the link provided, you'll get this:

**HTML**

```
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <title>JS Bin</title>
</head>
<body>

</body>
</html>
``` 
First thing, change the title:

```
<!DOCTYPE html>
<html>
<head>
  <meta charset="utf-8">
  <title>Asteroids Tutorial</title>
</head>
<body>

</body>
</html>
```

Now, we need to point to the simpleGame.js library, so we need to add this line:

```
<script src="http://binarytutor.x10.mx/HTML5-Asteroids/simpleGame.js">
</script>
```
somewhere in the `<head>` tag. How about right after the `<title>` tag?

So now, we have an HTML starting anchor. We'll add more later.

If you look at the top of the jsBin page, you'll see the JavaScript tab. Go ahead and click on it, so we can paste some code in it.

**JavaScript**

```
// Asteroids 

// Graphics and original code by anonymous

// Tutorial:
// http://www.codecademy.com/groups/html5-game-development/discussions/533d94509c4e9d98170035c2

/////////////////////////////
////////Game Constants 
/////////////////////////////


/////////////////////////////
////////Working Storage
/////////////////////////////


/////////////////////////////
////////Image file name functions
/////////////////////////////

/////////////////////////////
////////start Ship code
/////////////////////////////

/////////////////////////////
////////start Bullet code
/////////////////////////////

/////////////////////////////
////////start asteroid code
/////////////////////////////

///////////////////////////////
////////Alien code
//////////////////////////////


///////////////////////////////
////////start Collision Detection 
//////////////////////////////


///////////////////////////////
////////start Initialization code
//////////////////////////////

function init() {
} //end init()

///////////////////////////////
////////start update code
//////////////////////////////

function update() {
    
} //end update()
```
I know it doesn't look like much, but it is a start. 

# Asteroids: Lesson 2
**The Scene of Action**
Let's look through the JavaScript presented in the last lesson. It is mostly comments - place holders for the code we will be presently writing - but the crucial stuff for right now is at the bottom.

Two functions - `init()` and `update()` The first should be self explanatory, the second - maybe not so much. At the beginning of each game, the `init()` function gets executed, and is responsible for setting everything up. It gets executed once, and then it's done. The `update()` function, is the heartbeat of the game. It will be called about 10 times per second so that the code can do its thing, making objects move, scoring, etc. - that will come later.

So, want to have some fun? Go and put this line:
`alert("Here in init()");` 
inside the `init()` function, then click the "Run with JS" button located on the Output pane of your jsBin. What happens?

Nothing? 

Yep. Nothing. That's because we have yet to "wire up" the `init()` function so that it will get executed. How do we do that? Well, let me tell you! First, go to the HTML pane of your jsBin and find the `<body>` tag. Change it to look like this:
**HTML**

```
<body onload="init();">
```
and click that button again. 

Did you get an alert box? If so, then *good deal!* Progress!

Now, we need to install some more lines of code.

Copy
**Back to JavaScript**

```
var scene;          // Active Game scene - L2
```
right under the "Working Storage" section of the JavaScript.

Copy

```
var SCREEN_WIDTH = 600;        // Width of game screen - L2
var SCREEN_HEIGHT = 500;       // Height of game screen - L2
```
to Game Constants 

Copy 

```
  scene = new Scene(); // L2
  scene.setSize(SCREEN_WIDTH, SCREEN_HEIGHT); // L2
```
to a position *just above the `alert()`* command in the `init()` function, and test the page (by clicking "Run with JS" button).

What did you get? If everything is working correctly, you should get a big gray box in the output window, and the alert box. If not, something went wrong. Double check all the steps, and try again.

Ready to continue? If so, got one more line to copy to a point just above the `alert()` statement of the `init()` function:

```
  scene.setBG('black'); // L2
```  
When you click the "Run with JS" button now, what do you get? A big black box instead of the gray one? If so, *good show!* 

Here completes the lesson...


# Asteroids: Lesson 3
**Our Good Space Ship...**
So, in the previous lesson we got a playing field set up. Now, we will add our own space ship. There are many lines of code to add, so let's get to it.

Copy:

```
/*--------------------------------
   Image file names
*/

var IMG_PATH = "http://binarytutor.x10.mx/HTML5-Asteroids/Images/";  // Image base path - L3
var SHIP = IMG("SpaceShip.png",50,50);                               // Ship - L3
```
right under `SCREEN_HEIGHT` in the "Game Constants" section.

`IMG_PATH` is a constant which allows jsBin to find all the graphic images we will need in our game. `IMG()` creates a special "object" from which we can conveniently retrieve the name, width, and height of each graphic we use. 

Now copy:

```
var spaceShip;      // Player's ship sprite object - L3
```
right under `scene` in the "Working Storage" section.

Copy:

```
/*--------------------------------
   Create an object which contains the
   file name, width and hieght of
   a graphic image. Used to keep this
   information together in this script 
   file.
*/

function IMG(name, width, height) { // L3
    return {name:name, width:width, height:height};  // L3
}

/*--------------------------------
   Create a new Sprite object based on the
   information stored in parameter ImgO
   Return the created object to caller.
*/

function newSprite(ImgO) {  // L3
    return new Sprite(scene, IMG_PATH + ImgO.name, ImgO.width, ImgO.height);  // L3
}
```
right under "Image file name functions" of the JavaScript file.

Copy:

```
/*--------------------------------
   Create ship sprite.
*/

function Ship() { // L3
    var th = newSprite(SHIP); // L3
    return th;  // L3
}  //end Ship()
```
right under "start Ship code"

Copy:

```
  spaceShip = Ship(); // L3
```
right above the `alert()` in the `init()` function.

And finally, copy:

```
  scene.clear();      // L3
  spaceShip.update(); // L3
```
into the `update()` function.

At this point, we should talk about these last two statements. We've already mentioned that the `update()` function gets called 10 times a second, so the purpose of `scene.clear();` is to wipe the play field clear of all images. This allows `spaceShip.update();` to redraw the ship at possibly a new location. However, there are two more lines of code which need to be in place for all this magic to happen.

Copy:

```
var FPS = 10;                  // Frame rate - Frames per Second - L3
``` 
to a spot under "Game Constants" and copy:

```
  scene.start(FPS); // L3
```
Just *after* `alert()` in the `init()` function. 

The purpose of this last instruction is to start calling the `update()` function 10 times per second. The constant FPS stands for *Frames Per Second,* and is set to 10 at the top of the code. Once this statement is executed, things begin to happen in a hurry!

Now, we should be ready to test. Click on "Run with JS" button, to see the results.

If the ship moves sideways across the screen, *good show!*

Here endeth the lesson...

# Asteroids: Lesson 4
**Controlling Our Good Space Ship**
With the completion of our last lesson, we left our good space ship flying across the screen sideways. The first thing to do now is to correct the orientation, stop the ship, and center it in the play field, ready for the game user to take control!

To do this magic, we need to add three lines of code to the `Ship()` function, right under the line,

```
var th = newSprite(SHIP); // L3
```
which we put there in the previous lesson.

**NOTE:** As you install each of the lines of code below, click on the "Run with JS" button of the jsBin Output window and test the affect of each line on our program. 

Copy:

```
    th.changeImgAngleBy(90); // L4
``` 
This causes our ship to point into the direction of travel.

Now copy this line right under that last one:

```
    th.setSpeed(0); // L4
```
This statement will bring our ship to a stop.

Finally, this statement:

```
    th.setPosition(SCREEN_WIDTH / 2, SCREEN_HEIGHT / 2); // L4
```
Puts the ship dead center of our play field.

So, with all these elements in place, we are ready to give our player *command* of the ship. To do this, we need to add a function to our code.

Copy:

```
/*--------------------------------
   Check ship control keys...
*/

function keyChecks() {    // L4
}
```
right after the the closing bracket `}` of the `Ship()` function.

Next, copy this line:

```
  keyChecks(); // L4
```
right under `spaceShip.update();` of the `update()` function.

**NOTE:** You are invited to test the code, but don't expect any keystrokes to make the ship move - yet.

So, now let's add a some code to allow the player to move the ship forward.

Copy:

```
var MAX_SHIP_SPEED = 30;       // Maximum speed of ship - L4
```
right under `SCREEN_HEIGHT` in the "Game Constants" section.

Then add this line inside the `keyChecks()` function:

```
  if (keysDown[K_UP] && spaceShip.getSpeed() < MAX_SHIP_SPEED)  // L4
    spaceShip.changeSpeedBy(2); // L4
```
So, what's going on? First, the `keysDown[]` array is a gift from the simpleGame library we are using. Each `true` element it contains represents a key on the keyboard that is being held down. If the element is false, then the corresponding key is *not* down. Another gift from the library is the variable `K_UP` It just happens to contain the key code of the - you guessed it - up arrow key. 

Now, the rest of the `if()` expression might be a little confusing.  The `spaceShip.getSpeed() < MAX_SHIP_SPEED` compares the current speed of our ship with a maximum speed contained in `MAX_SHIP_SPEED` As long as we aren't going too fast, the second line , `spaceShip.changeSpeedBy(2);` is executed. Can you guess what it does?

Once all those lines are installed, go ahead and test. Pushing the up arrow should start our ship moving - but getting it stopped again - well, let's just say we need more code...

Ok, so now we want to be able to slow down our ship, and even go backward. Here is the code to do that.

```
  if (keysDown[K_DOWN] && spaceShip.getSpeed() > -MAX_SHIP_SPEED) // L4
    spaceShip.changeSpeedBy(-1); // L4
```
Same deal as before, only now we test for the down arrow key, and we've inverted the test for the maximum speed. Install and test.

In addition to going forward and reversing, it kind of would be nice to *steer* our ship. So, again, more code:

```
  if (keysDown[K_LEFT]) // L4
    spaceShip.changeAngleBy(-10); // L4
```
So now we are looking at the left arrow key to rotate the ship 10 degrees counter-clockwise. But it *kinda* would be nice to turn the *other* way as well, so, a few more lines of code:

```
  if (keysDown[K_RIGHT])  // L4
    spaceShip.changeAngleBy(10); // L4
```
Does it look a little familiar? The above lines will allow the right arrow key to steer the ship clock-wise. By all means, check it out!

Now, we aren't quite done with this `keyChecks()` function as we have one more key to test for - the all important FIRE button!

Stay tuned, Space Cadets! There is more to come soon! In the meantime, go   log some flight time...

# Asteroids: Lesson 5
**Ready! Aim! FIRE!**
In the last lesson, we got our spaceship flying through space under user control. Since the object of this game is to shoot asteroids and other things, we need a gun. Our gun shoots bullets. We want to be able to shoot a stream of bullets at targets that fly dangerously close to us. So, let's get started.

First, there are a number of constants we should add to our growing game program. They are:

```
var NUM_BULLETS = 10;          // Maximum simultaneous bullets that can fly - L5
var BULLET_DELAY = 5;          // Number of update frames between bullet firing - L5
var BULLET_SPEED = 20;         // Base speed of bullet - L5
var BULLET_LIFE = 20;          // Number of frames bullet flies - L5
var SPREAD = 1;                // Degrees of spread of bullet trajectory - L5
```
Install these right under `MAX_SHIP_SPEED` in the "Game Constants" section.

All of these should be understandable based on the comment after each one. This last "constant" has to do with the bullet's graphic file:

```
var BULLET = IMG("Bullet.png",10,10);                  // Bullet
```
right under `SHIP` in the "Image file names" section.

We need a new line in the "Working Storage" section:

```
var bullets;        // Array of bullet sprite objects - L5
```
right under the `spaceShip` variable.

You might ask, "Why does `bullets` need to be an array?" Because we want *more than one bullet at a time to shoot!* By putting the bullet sprites into an array, we can perform all the necessary operations we want like shooting them, updating them, and ending them using simple loops. Saves a *lot* of code.

Now, we need a function which will create a sprite for a single bullet:

```
/*--------------------------------
   Create bullet sprite.
*/

function Bullet() { // L5
    var th = newSprite(BULLET); // L5
    th.hide(); // L5
    return th; // L5                   
} //end Bullet()

```
Install it right into the "start Bullet code" section.

It's purpose is to call the `newSprite()` helper function with the parameter `BULLET` IMG object, hide the sprite, and return the newly created Sprite object to the calling function. 

Now, we need code to call this bullet creating code, and store the returned object:

```
/*--------------------------------
   Create and log all bullet sprites.
*/

function makeBullets(){ // L5
  var i; // L5
  bullets = []; // L5
  for (i = 0; i < NUM_BULLETS; i++)  // L5
    bullets.push(Bullet()); // L5
} // end makeBullets
```
Install it right under the closing bracket `}` of the `Bullet()` making function above. 

The above code first creates a new, empty array called `bullets`, then it uses the `push()` method to append a bullet sprite to the `bullets` array. It uses the `NUM_BULLETS` constant to control the number of iterations through the loop, and thus the number of bullets created.

It should be noted that the `Bullet()` function is *only* called during the initialization phase of the game! Even though the player will be able to fire an *unlimited* number of bullets, only a small number of bullet sprites will be used - over and over again. Stay tuned to see how that is done!

Now, let's install the `makeBullets()` function into the `init()` function and do some testing:

```
  makeBullets(); // L5
```
right above the `alert()` call inside the `init()` function, and test.

Anything happen?

Well, if you did everything right, you should still be able to drive your ship. But, alas, no shooting is possible.

More code. Copy:

```
/*--------------------------------
   Animation code for bullet sprites.
*/

function updateBullets(){ // L5
  var i, th; // L5
  for (i = 0; i < bullets.length; i++){ // L5
    if ((th = bullets[i]).visible) { // L5
      th.update();  // L5
    }
  } // end for
} // end updateBullets 
```
right *above* the "start asteroid code" section of the program.

Next, copy:

```
  updateBullets(); // L5
```
right after the `keyChecks();` statement in the `update()` function of the program. 

And test.

Still no bullets? But you should still be able to fly your ship.

So, another block of code:

```
/*--------------------------------
   Ship fires a bullet sprite.
*/

function fireBullet () { // L5
  var i, th; // L5
  // Loop through available bullets  // L5
  // looking for an available sprite...   // L5
  for (i = 0; i < bullets.length; i++) {   // L5
    if (!(th = bullets[i]).visible) {   // L5
      // Set angle of bullet motion... // L5
      th.setMoveAngle(-90 + spaceShip.getImgAngle() + Math.random() * SPREAD - SPREAD / 2); // L5
      // Now the speed, based on how fast ship is moving.
      th.setSpeed(spaceShip.getSpeed() + BULLET_SPEED);
      // Start bullet at location of ship. .. // L5
      th.setPosition(spaceShip.x, spaceShip.y); // L5
      // Make bullet visible. // L5
      th.show();   // L5
      return; // L5
    }
  }
}
```
Install it just above the "start asteroid code" section of the program.

This is where the power of looping comes in. By putting all those bullet sprites into an array, we can just loop over all of 'em and perform the necessary steps to make 'em fly. 

Those steps include: setting the bullet's angle of motion, (same as direction that the ship is pointing) + a random spread factor; the bullet speed (ship speed plus a constant); and starting point (the center of the ship sprite). 

So now test. Can you still fly your ship? You should.

Ok, ok. By now, you are probably all asking the same question, to wit: when will we get to fire bullets?!? Well, remember the `keyChecks()` function? We said there was one more key we needed to check for, and this is it:

```
  if (keysDown[K_SPACE]) // L5
    fireBullet(); // L5
```
It needs to be installed right under `spaceShip.changeAngleBy(10); ` in the `keyChecks()` function. When the player pushes the space key, a stream of bullets should come out...

Now, during testing, can you still fly your ship? Can you press the space bar and shoot bullets? 

Notice any problems? "Hey!" you say, "The bullets just keep flying, and when we run out, no more firing! What gives?" Well, the answer my friend, is the same as before...we need more code.

Let's see if we can address the problem of bullets not dying:

```
      // Bullet flight time... // L5.1
      th.bulletLife = BULLET_LIFE; // L5.1
```
just under the `th.show();` statement in the `fireBullet ()` function.

That sets up a counter which will control how long a bullet lives. Now, it needs to be used somewhere:

```
      if (th.bulletLife > 0)  // L5.1
        th.bulletLife--;  // L5.1
      else                   // L5.1
        th.hide(); // L5.1
```
just under `th.update();` of the `updateBullets()` function. 

Test again. What happens now?

You should be able to fire a stream of bullets, then the bullets die, and then you can shoot again.

But there is *still* one little problem: if you hold the space bar down, a whole group of bullets fire all once. So, we should probably fix that.

First, we need another variable:

```
var bulletTimer;    // Regulates number of simultaneous bullets fired by player 
                    // Measured in update frames // L5
```
just under `bullets` in the "Working Storage" section. 

Now, copy:

```
  // This regulates the number of simultaneous  // L5.1
  // bullets that can be fired.  // L5.1
  if (bulletTimer > 0)  // L5.1
    bulletTimer--;  // L5.1
```
to a position just above the closing bracket `}` of the `updateBullets()` function.

Copy:

```
  // If too soon to fire a bullet, // L5.1
  if (bulletTimer > 0)  // L5.1
    // Do nothing...  // L5.1
    return;  // L5.1
```
just under `var i, th;` of the `fireBullet ()` function. 

Now test. Notice a difference? 

# Asteroids: Lesson 6
**WARNING: Asteroids approaching!**
In the previous lessons, we got to the point where we can drive our ship and shoot bullets. But that isn't really a lot of fun, is it? No, we need *something to shoot at* to make this an interesting game.

Believe it or not, we will use the same basic logic for asteroids that we used for the bullets. Each new asteroid sprite (and there are three different *sizes* of them) will get loaded into an array so that we can iterate over them and make them fly. Later, we will use a simple 2 level nested loop to iterate over bullets and asteroids, looking for collisions. Also, we will iterate over the asteroids looking for a collision with our good space ship (this adds *challenge* and *suspense* to the game).

So, with this basic outline, let's get to it.

We start, as before, with new constants. They are:

```
var NUM_ASTEROIDS = 2;         // Number of large asteroids in game - L6
var NUM_SMALL_ASTEROIDS = 1;   // " small asteroids - L6
var NUM_TINY_ASTEROIDS = 1;    // " tiny asteroids - L6
``` 
Install them just under `SPREAD` in the "Game Constants" section.

Their purpose is to gather in one convenient place the number of each kind of asteroid we want. The actual number in *your* version is quite up to you. Me being a fumble fingered wanna be video game superstar, I set the total number quite low so I can test the game. Your mileage may vary.

Next, we have some more `IMG` objects to add. They are:

```
var ASTEROID = IMG("Asteroid.png",150,150);            // Large Asteroid - L6
var SMALL_ASTEROID = IMG("SmallAsteroid.png",100,100); // Small Asteroid - L6
var TINY_ASTEROID = IMG("TinyAsteroid.png",75,75);     // Tiny Asteroid - L6
```
They should be installed under `BULLET` in the " Image file names" section of our game program.

Remember that array I mentioned? It's next:

```
var asteroids;      // Array of asteroid sprite objects - L6 
```
It gets installed right after `bullets` in the "Working Storage" section.

Now, some code. First up, is a function which makes new asteroid sprites. 

```
/*--------------------------------
   Create large asteroid sprites.
*/

function Asteroid() { // L6
    var th = newSprite(ASTEROID); // L6
    return th; // L6        
} //end Asteroid()
```
Install it in the "start asteroid code" section of the game.

It really is very simple - now. It creates a new sprite based on the `ASTEROID` object, and returns it to the caller. We will be adding more code to it later. 

As always, you should test your code at this point to make sure it still works - drive ship, shoot bullets. 

More code:

```
/*--------------------------------
   Create all large, small, and tiny asteroid sprites.
*/

function makeAsteroids() { // L6
    var i; // L6
    asteroids = []; // L6
    for (i = 0; i < NUM_ASTEROIDS; i++) // L6
        asteroids.push(Asteroid()); // L6
} //end makeAsteroids()
```
Install it right under the closing bracket `}` of the function above.

Never mind the comment, "Create all large, small, and tiny asteroid sprites." as we will work with just one size of asteroid at a time.

Test your code...

This function, `makeAsteroids()` performs magic - it produces a *number* of large asteroids and puts the sprite objects in the `asteroids[]` array using the `push()` method. The number of those sprite objects created is controlled by - you guessed it - the value of `NUM_ASTEROIDS` 

So, here's a question for you: where to you need to install the *call* to this function, `makeAsteroids()`? Think about it...If you said, in the `init()` function, you'd be right. Because `makeAsteroids()` need only be called *once* at the beginning of a new game - that's all. How can this be? Simple...we will add code to `hide()` method the asteroid when it is hit by a bullet, and the `show()` method to reuse it at the appropriate time. 

Ok, let's install the call now:

```
  makeAsteroids(); // L6
```
Install it right after `makeBullets();` in the `init()` function.

Of course, test your code. Don't be surprised that you don't see any asteroids just yet, because there is more code to do.

Can you still drive and shoot?

Good! Now, we need code to update the asteroids on the screen each time the `update()` function is called.

```
/*--------------------------------
   Animate asteroid sprites.
*/

function updateAsteroids() { // L6
    var i, th; // L6
    // Loop through all asteroids...  // L6
    for (i = 0; i < asteroids.length; i++) {  // L6
        // Is asteroid visible?  // L6
        if ((th = asteroids[i]).visible) {  // L6
           // Yes, animate it... // L6
           th.update(); // L6
        }
    }
}
```
Install the above code right after the closing bracket `}` of the `makeAsteroids()` function in the "start asteroid code" section of the game.

What does it do? Well, for right now, all it does is iterate through the array of asteroid sprites in the `asteroids[]` array and calls the `update()` method. 

Test your code. Now, one more piece before we can have asteroids flying around our ship:

```
  updateAsteroids(); // L6
```
Gets installed right after the `updateBullets();` function call in the `update()` function. 

Test code. What do you have?

If you got everything right, you'll get a *single* large asteroid flying from left to right on your screen. Not what you expected, huh? I bet you expected to see *two* asteroids, right?

How do we fix that? As usual...more code.

Look at this line:

```
    th.setDY(Math.random() * 8 + 5); // L6.1
```
Install it right after `var th = newSprite(ASTEROID);` in the `Asteroid()` function. 

Test again. See a difference?

It's purpose is to give the two asteroids a *different* speed vector in the y direction. Let's see if we can do better:

```
    th.setDX(Math.random() * 8 - 5); // L6.2
```
Install it right after `th.setDY(Math.random() * 8 + 5);` in the `Asteroid()` function.

Test. Is that better? 

Now, one more line of code. This one:

```
    th.setPosition(0, 0);  // L6.3
```
Install it right after `th.setDX(Math.random() * 8 - 5);` in the `Asteroid()` function.

Test again. 

This line of code causes the asteroids to start in the upper right corner of the screen.

One last feature to add, before we call it quits for this lesson. (I think this is kind of cool, so I hope you'll just follow along and see for yourself.)

Get this line:

```
    th.deltaAngle = Math.floor(Math.random() * 5 + 2); // L6.4
```
And install it right after `th.setPosition(0, 0);` in the `Asteroid()` function.

Take these lines:

```
           // Rotate the asteroid as it floats through space // L6.1
           th.changeImgAngleBy(th.deltaAngle);  // L6.1
```
and install them right after `if ((th = asteroids[i]).visible) {` in the `updateAsteroids()` function.

And test. Pretty cool, huh?

The beauty of using a library like simpleGame.js is that this simple effect - rotating objects - came at a fairly cheap price - two lines of code in the right place! All the hard work of manipulating the `<CANVAS>` tag was already taken care of - so, why not take advantage of it?

Until next time, Space Cadets...

# Asteroids: Lesson 7
**Detecting and Handling Collisions**
So, in previous lessons, we got a ship, bullets, and asteroids harmoniously flying around with one another. How sweet! Bliss is ours!

Right....

This is a *video game*...and we want to *destroy* things!

Well, let's get to it, then.

First, we need to add some more infrastructure to the code. Copy:

```
  checkCollisions(); // L7
```
just under `updateAsteroids();` in the `update()` function.

Then, install this code:

```
function checkCollisions() { // L7
    var i, j, th;  // L7
} //end checkCollisions()
```
in the "start Collision Detection" section of the game code.

This creates for us a basic framework for our collision detection logic. On each update of the screen, we will look to see which objects have collided with one another, and then do something. 

First, let's start with bullets and asteroids:

```
  // For each bullet... // L7.1
  for (i = 0; i < bullets.length; i++) { // L7.1
    // Check for bullet hitting asteroid... // L7.1
    for (j = 0; j < asteroids.length; j++) {  // L7.1
      if (bullets[i].collidesWith(asteroids[j])) { // L7.1
        // bullet-asteroid Collision detected... 
      }
    }
  }
```
Install it just under `var i, j, th;` in the `checkCollisions()` function.

Test your code. 

What we have done is create two nested loops over the `bullets[]` array and the `asteroids[]` array, and used the sprite method `collidesWith()` to determine if the indexed objects have collided. When such a collision is detected, the code marked by the comment `// bullet-asteroid Collision detected...` is executed. Obviously, there is nothing yet to execute, so let's add something.

Add this line under the comment `// bullet-asteroid Collision detected...`:

```
        bullets[i].hide(); // L7.2
```
Care to guess what that line does?

Well, check your hypothesis by testing your code. Be sure to shoot at the asteroids...

If you said, "bullets disappear when they hit an asteroid," you would be right! So, let's make the *asteroid* disappear, too! Install this line of code:

```
        asteroids[j].hide(); // L7.3
```
...right after the `bullets[i].hide();` in the `checkCollisions()` function.

Test your code. What happens now when you shoot asteroids?

There's an old country-western tune methinks appropriate: *Alone again...*

Yep. The asteroids go away...but don't come back, right?

That is actually what's supposed to happen at this point. And do you know how we need to fix it? One guess...more code.

Copy this line:

```
        asteroids[j].spawnCnt = Math.floor(30 + Math.random() * 20); // L7.4
```
right after `asteroids[j].hide();` you just installed above.

What it does is establish a counter, `spawnCnt`, as a property of the asteroid sprite that just got hidden. The value is determined at random. But what to do with it?

Well, as each update occurs, we can decrement it by one, until it reaches zero, at which point we can `show()` the asteroid again.

Sound good? Ok, install this code:

```
        // Has delay before spawn expired? // L7.5
        else if(th.spawnCnt > 0)  // L7.5
            // No, reduce count // L7.5
            th.spawnCnt--; // L7.5
        else { // L7.5
            // Make asteroid visible again  // L7.5
            th.show();  // L7.5
            // And draw it on the screen...  // L7.5
            th.update();  // L7.5
        }
```
after the *closing bracket* `}` of the `if ((th = asteroids[i]).visible) {` of the `updateAsteroids()` function.

Now test your code...

If all is well with your code, then you should be able to shoot an asteroid, causing it to disappear for a few seconds, and then watch it reappear. 

Now, if you test your code long enough, you should also note that the asteroid may sometimes reappear right over your ship. This isn't a problem now, but when we add code to detect collisions between ships and asteroids, it *will* be a problem - trust me.

We could wait till later to fix this, but let's just go ahead and do it now. Copy this line:

```
            // Reset the position of asteroid // L7.6
            th.setPosition(0, 0); // L7.6
``` 
to a position between `th.show();` and `th.update();` in the `updateAsteroids()` of the code presented above. 

Test your code. Notice a difference?

Now, when an asteroid comes back, it reappears in the same position each time, so that our ship can stay well away from it during play.

So, in the next lesson, we will deal with scoring when a bullet hits an asteroid.

# Asteroids: Lesson 8
**Scoring**
In previous lessons, we got our ship flying and under control; added bullets and asteroids; and collision detection between bullets and asteroids. Next, we tackle the problem of score keeping, because, after all, what fun is a game where you can't brag about your prowess?

This Asteroids version tracks lives and score. Each time your ship collides with an asteroid, you die - or loose a life, as it were - while each time one of your bullets destroys an asteroid, you get so many points. 

For the benefit of your player, we need to post the current score and remaining lives on the screen somewhere. Since we have a basic bit of HTML in this game, the simplest way to do that is to create a div element where the score and lives remaining can be displayed using a `<DIV>` tag's `innerHTML`  property. So, to start off, copy this code:
**HTML**

```
    <div id="msgBoard"></div>
```
between `<body onload="init()">` and `</body>` tags. 

Now, copy these lines:
**JavaScript**

```
var LIVES = 3;                 // Number of lives player starts game with - L8

var SCORE_ASTEROID = 3;        // Number of points awarded when bullet hits large asteroid - L8
var SCORE_SMALL_ASTEROID = 7;  // " small asteroid - L8
var SCORE_TINY_ASTEROID = 12;  // " tiny asteroid - L8
```  
just under `SPREAD` of the "Game Constants" section.

These constants sets the starting number of lives per game, and the number of points awarded for destroying each size of asteroid the game supports. (Don't worry that we don't use them just yet) 

Next, we need some variables to track the HTML element object, score, and lives remaining:

```
var msgBoard;       // HTML element where score and lives are displayed - L8
var life;           // Current remaining player lives - L8
var points;         // Current player point total - L8
```
Install them just above the `scene` variable in the "Working Storage" section.

Now, before we go to the `init()` function and initialize these new variables, let's add the code to display the score and lives remaining:

```
/*--------------------------------
    Add amount of points to current score
    Display score and life count 
*/

function addPoints(amount) { // L8
    points += amount; // L8
    msgBoard.innerHTML = "<b>Score:</b> "+ points + ", <b>Lives:</b> " + life; // L8
}
```
Install them just under the comment for the "start Ship code" section.

Notice that this function does three things all at once:
1) Updates the current score with the input parameter `amount`
2) Displays the new current score
3) Displays the life remaining.

Now, whenever we want to update the score as a result of a collision between a bullet and asteroid, we call `addPoints(amount)` with a positive `amount` But there are also two other times we can use it by calling it with 0: at the start of the game, and when we loose a life. 

We'll see how in a few moments.

Now, prudence should dictate we test our code to make sure everything still works the way it should. Go ahead and do that now - I'll wait....

Back? Everything still OK? Good! I knew you could do it!

So, we need to initialize all those variables we just introduced. So, go down to the `init()` function, and install these lines:

```
  life = LIVES; // L8
  points = bulletTimer = 0; // L8
  msgBoard = document.getElementById('msgBoard'); // L8
```
You may put them just above the `scene = new Scene();` statement.

BTW: notice how the `bulletTimer` is being set to zero? That was an oversight from previous lessons we are just getting around to correcting. It's always a good idea in a complex program like this one to initialize your variables to a known value.

Now, remember that pesky `alert()` statement in the `init()` code? Are you *tired* of it already? I know I am! But, believe it or not, it did serve a valuable purpose: if the alert box came up when you started a test, then odds are all is ok with the initialization phase of your game code. Now, we have a more elegant way of achieving that same thing *without* having to mash the Enter key every time we test - just look for "**Score:** 0, **Lives: 3** just above your play field.  

So, go ahead and *replace* that `alert()` function with:

```
  addPoints(0); // L8.1
```
(Just in case you already nixed that ol' `alert()` call, just copy the above line right above the `scene.start(FPS);` statement.)

Now, test your code. 

Everything still working? What's that? No score increase when you shoot an asteroid? Well, that's ok. Because we need to add a few more lines of code in the right spot for that to happen.

So, remember those constants that held the number of points for each rock? Here is where we need to use them (or at least the first one):

```
    th.spawnCnt = 0; // L8
    th.hitPoints = SCORE_ASTEROID; // L8
```
It gets installed in the `Asteroid()` function just above the `return th;` statement. 

BTW: `th.spawnCnt = 0;` is also a correction of an oversight like the `bulletTimer` one, and for the same reason. 

Now, one more thing to do:

```
        addPoints(asteroids[j].hitPoints); // L8
```
Gets installed just under `asteroids[j].spawnCnt = Math.floor(30 + Math.random() * 20);` in the `checkCollisions()` function. 

Now, test your code. Does scoring work when you shoot the asteroid?

In the next lesson, we'll handle ship death...


# Asteroids: Lesson 9
**Death in Space**
Of all the ways one might shed this mortal coil, I'm betting that breathing vacuum is likely to be right up there on the list of Very Quick and Painless.  

In this game, there are three ways to loose a "life," namely: collision with an asteroid, collision with an alien ship, or getting hit with an alien laser. In this lesson, we'll be adding the code for collision with asteroids.

Let's get started!

First, install this code:

```
  // Check for ship hitting asteroid // L9
  for (j = 0; j < asteroids.length; j++)  // L9 
    if (spaceShip.collidesWith(asteroids[j])) {  // L9
      asteroids[j].hide();  // L9
      asteroids[j].spawnCnt = Math.floor(30 + Math.random() * 20);  // L9
      die(); // Lose a life... // L9
      return;  // L9
    }
```
right after the closing bracket `}` of this loop: `for (i = 0; i < bullets.length; i++) {` in the `checkCollisions()` function. **Caution:** There are *two* loops in that function, nested within each other, and we want this code to appear right after the *outer* loop.

Let's study it a little. First, we are looping through the array of asteroids, checking to see if our good ship is in collision with one. Then, when we detect such a collision, we will hide the asteroid, and set it's `spawnCnt` property to a random value, and finally call a function called `die()`

Yeah, yeah - we haven't defined it yet, so that's next.

Install this code:

```
/*--------------------------------
   Ship loses a life...
*/

function die() { // L9
    life--; // L9
    addPoints(0); // L9
} //end die()
```
right after the closing bracket `}` of the `addPoints()` function. 

What does it do? Well, it should be obvious that it reduces the life counter by one, and then calls `addPoints()` with zero to update the score and life display for the player.

So, let's test the code...Dum...Dee...Dum

Done testing? What did you observe when you collided with asteroids? You should have seen the life counter be reduced by one for every collision, but when it got down to zero, the game didn't end - the life counter just went into negative territory!

So, as usual, the fix for this problem is to add code...

This code:

```
    if (life <= 0) { // L9
        alert("Game Over! Your score was: " + points); // L9
    } //endif
```
right after `addPoints(0);` in the `die()` function.

And test. Any difference? The line `if (life <= 0) {` tests for the condition where life is less or equal to zero, and then throws up an alert box, but after you "Ok", the game just keeps on going, right? So, we need one more line to fix that problem:

```
        scene.stop(); // L9.1
```
should be installed right after `if (life <= 0) {` in the `die()` function.

And test. What happens now? the line `scene.stop();` calls a method of the `scene` object which turns off the calls to the `update()` function, bringing the animation to a stop. 

So, this is the basic game. What's left to do is add more asteroids, alien ships, and alien lasers to complete this project.

Next lesson, we'll add more asteroids which, as it turns out, will be pretty simple because of all the infrastructure we have in place.

# Asteroids: Lesson 10
**Let there be MORE asteroids!**
So far, we can drive our ship, shoot asteroids, and loose virtual life by colliding with asteroids. In this lesson, we'll add more asteroids to increase the challenge. 

Remember this constant? 

```
var NUM_ASTEROIDS = 2;         // Number of large asteroids in game - L6
```
If you wanted to add more large asteroids, all you'd have to do is change 2 to some number that is larger - like maybe 6 or so. 

If you haven't already, maybe you should go ahead and do so now. I'll wait.

Dum...Dee...Dum...

Back? Well, more larger asteroids may certainly be nice, but how about a *smaller* asteroid? Well, before we start, let's look at a function we added in Lesson 6:

```
function Asteroid() { // L6
    var th = newSprite(ASTEROID); // L6
    th.setDY(Math.random() * 8 + 5); // L6.1
    th.setDX(Math.random() * 8 - 5); // L6.2
    th.setPosition(0, 0);  // L6.3
    th.deltaAngle = Math.floor(Math.random() * 5 + 2); // L6.4
    th.spawnCnt = 0; // L8
    th.hitPoints = SCORE_ASTEROID; // L8
    return th; // L6        
} //end Asteroid()
```
As it turns out, we can add a small asteroid using this code as a *template* and making a few edits. First, some infrastructure:

```
/*--------------------------------
   Create small asteroid sprites.
*/

function SmallAsteroid() { // L10
} //end SmallAsteroid()
```
should be added right after the closing bracket `}` of the `Asteroid()` function.

Of course, this empty function won't do anything yet, so we have to fill it in.

First, 

```
var th = newSprite(ASTEROID); // L10
``` 
needs to be added to the `SmallAsteroid()`, but `ASTEROID` needs to be changed. Your choices are either `SMALL_ASTEROID` or `TINY_ASTEROID`

Now, right after that line, you need to add two more:

```
    th.setDY(Math.random() * 8 + 5); // L10
    th.setDX(Math.random() * 8 - 5); // L10
```
but change the `+ 5` of the `th.setDY()` statement to `+ 7` That will give the small asteroid a slightly different random direction from the large asteroid.

Now, put this line:

```
    th.setPosition(0, 0); // L10
```
right after `th.setDX()` statement. 

Now, for this line:

```
    th.deltaAngle = Math.floor(Math.random() * 5 + 2); // L10
``` 
only change the `* 5` to `* 10` to give the small asteroid a slightly different random spin.

Add this line unchanged:

```
    th.spawnCnt = 0; // L10
```

Now this line,

```
    th.hitPoints = SCORE_ASTEROID; // L10
```
But first, we need to change `SCORE_ASTEROID` to either `SCORE_TINY_ASTEROID` or `SCORE_SMALL_ASTEROID` 

(In case you haven't figured it out, we're coding the *small* asteroid here, so you should choose the corresponding *small asteroid* constant.)

Finally, this line:

```
    return th; // L10
```
is needed to finish the function. 

At this point, we've added a sufficient amount of code that we should test to make sure we haven't broken anything. Don't expect to see any small asteroids just yet. 

Can you still drive your ship, shoot asteroids for points, crash into asteroids and loose lives? Good!

Now, we have just written a function which creates for us small asteroid sprites, but we haven't added code to *call* it yet. So, that's up next.

Remember the `makeAsteroids()` function? We claimed in a comment that it would eventually create all three kinds of asteroid sprites - large, small and tiny - so now we will add needed code to fulfill two out of those three promises. These are two *existing* lines of that function:

```
    for (i = 0; i < NUM_ASTEROIDS; i++) // L10
        asteroids.push(Asteroid()); // L10
```
It requires *two* modifications to server our purposes, to wit: change `NUM_ASTEROIDS` and `Asteroid()` 

Guess what? I'm not gonna tell you in this lesson what you need to change those two items to. Consider this a mid-term exam.

When you get done modifying the above two lines, *add it* following the original `for()` loop in the `makeAsteroids()` function.

Test your code. You should have two sizes of asteroids floating around, and be able to shoot them, and crash into them...

Now, you should be able to noodle out how to add the tiny asteroid on your own. I encourage you to try. In the next lesson, though, we'll walk through adding the *tiniest* asteroid...

# Asteroids: Lesson 11
**MORE Asteroids (continued)**
Well, Space Cadets, I'm back. Ready for more progress on our game? 

Good! Let's get started.

For those of you who were unable to get the code for small and tiny asteroids to work, I present the necessary code here:

```
/*--------------------------------
   Create small asteroid sprites.
*/

function SmallAsteroid() { // L10
    var th = newSprite(SMALL_ASTEROID);  // L10
    th.setDY(Math.random() * 8 + 7); // L10
    th.setDX(Math.random() * 8 - 5); // L10
    th.setPosition(0, 0); // L10
    th.deltaAngle = Math.floor(Math.random() * 10 + 2); // L10
    th.hitPoints = SCORE_SMALL_ASTEROID; // L10
    th.spawnCnt = 0; // L10
    return th; // L10
    
} //end SmallAsteroid()

/*--------------------------------
   Create tiny asteroid sprites.
*/

function TinyAsteroid() { // L11
    var th = newSprite(TINY_ASTEROID); // L11
    th.setDY(Math.random() * 8 + 10); // L11
    th.setDX(Math.random() * 8 - 10); // L11
    th.setPosition(0, 0); // L11
    th.deltaAngle = Math.floor(Math.random() * 20 + 2); // L11
    th.hitPoints = SCORE_TINY_ASTEROID; // L11
    th.spawnCnt = 0; // L11
    return th; // L11
    
} //end TinyAsteroid()
```
All of the above code gets installed right after the `Asteroid()` function of the game code. 

These lines:

```
    for (i = 0; i < NUM_SMALL_ASTEROIDS; i++) // L10
        asteroids.push(SmallAsteroid()); // L10
    for (i = 0; i < NUM_TINY_ASTEROIDS; i++) // L11.1
        asteroids.push(TinyAsteroid()); // L11.1
```
get installed right under `asteroids.push(Asteroid()); // L6` in the `makeAsteroids()` function.

Now, test your code. If everything is done correctly, you should have three sizes of asteroids floating around, be able to shoot and destroy each kind, receiving a *different* point value for each size - smallest number of points awarded for the largest asteroid, and the largest amount for the smallest asteroid.

Each asteroid should be floating around on a slightly different path, rotating at a slightly different speed. 

In our next lesson, we'll add alien space ships on the attack...

# Asteroids: Lesson 12
**The Space Aliens are Coming!**
Ok, Space Cadets! One burning question of our time is, "Are we alone?" I suppose the people who are most interested in answering that question in the affirmative *assume* extra-terrestrial life forms will be *friendly...* But what if they aren't? What if they're like the Martians in H.G. Well's classic, "War of the Worlds?" Or the Hollywood original, "Independence Day," starring Will Smith? What if space aliens turn out to be *meaner, nastier, more aggressive* than *we are?*

What then?

Well - we shoot 'em! Get out that big 'ol particle beam weapon, "Bizz!! Bizz!!" Fry those critters! We've got a *big hunkin' galactic shooting gallery out there! Just waiting for us!* Never mind that such a weapon does not yet exist...

Hmmph!

Truly, for all those poor little kiddies quaking in their sneakers, methinks we really don't have much to worry about. The distances between us and any potential nasty space alien monsters is such that even *if* they knew where to find us, the time it would take to get here means we'd have to wait a *very, very long time...* 

But, what would a good arcade game be without invading space aliens to attack us, hmmm? 

Now, the Space Aliens we are going to implement in this lesson will pack a double punch - if our ship hits one, we loose a life. And if one of their lasers hits us, same thing - we loose a life. 

Our bullets have no effect on their lasers, but if we destroy the alien ship which powers it, both the alien ship and its laser is destroyed, and we earn a few points. 

So, all funny business aside, let's get to programming!

First, there are several new game constants we need to set up. 
Copy this one:
```
var SCORE_ALIEN = 50;          // " alien ship - L12
```
just under `SCORE_TINY_ASTEROID` in the "Game Constants" section of the program. This is the number of points awarded each time we destroy an alien space ship.

Copy this one:
```
var NUM_ALIENS = 3;            // Number of alien ships flying through game - L12
```
right under `NUM_TINY_ASTEROIDS` of the same section. This will control the total number of aliens permitted to hassle our poor ship.

Next, these two:
```
var ALIEN = IMG("Alien.png",40,50);                    // Alien Ship - L12
var ALIEN_LASER = IMG("AlienLaser.png",5,5);           // Alien Laser - L12
```
gets copied right under `TINY_ASTEROID`, which are the last of the sprite images we need for this game. 

Now, another array to hold the alien sprites:
```
var aliens;         // Array of alien ship objects - L12
```
Which gets installed right after `asteroids` in the "Working Storage" section of our program. It is the last of the variables we need.

Now, we have to deal with the code which uses these constants and variables:
```
/*--------------------------------
   Create alien sprites.
*/

function Alien(i) { // L12
    // local variable th holds the alien sprite object
    var th = newSprite(ALIEN);  // L12
    // Function to set the spawnCnt at random for alien sprite...
    th.spawnCntFun = function(i) {  // L12
        this.spawnCnt = Math.floor(30 * i + Math.random() * 15);  // L12
    };
    // Set the spawnCnt
    th.spawnCntFun (i);  // L12
    // Hide the alien until spawnCnt reaches 0
    th.hide(); // L12
    // Alien laser init stuff goes here...
    return th;   // L12
}
```
This gets installed in the "Alien code" section of the game. Let's analyze it a bit.

We should all recognize `function Alien(i)` as the opening of a function definition. This function's purpose is to do all the work of creating an alien sprite object. One thing different about it and the asteroid sprite creator functions is the parameter `i` - which is the index of the sprite object, starting from zero, to the maximum number of aliens minus 1. It will allow us to make the alien sprites slightly different one from another. 

Next comes `var th = newSprite(ALIEN);` Certainly by now it should be familiar - it calls our simpleGame library to create a raw sprite object based on the information contained in the `ALIEN` IMG object. 

Then,  
```    
th.spawnCntFun = function(i) {  // L12
        this.spawnCnt = Math.floor(30 * i + Math.random() * 15);  // L12`
};
```
which is pretty different than anything we've seen before. It creates an object *method* to randomly create the `spawnCnt` value. Also, it uses the `i` index variable to adjust the base range of this value, meaning that each alien will appear slightly staggered on first appearance and thereafter each time it is destroyed.

Then, we have `th.spawnCntFun (i);` which actually *calls* the method we just created for the first time, so that after the game starts up, our aliens will begin to appear.

Next, `th.hide();` which prevents the alien ship from appearing right off the bat. When the `spawnCnt` value reaches zero, then the corresponding alien sprite will appear, 

The comment about "Alien laser init stuff" is just a placeholder. We'll get to it in another lesson...

Lastly, `return th;` returns the newly created sprite object to the calling function.

At this point, you should test your code to see if all this new code hasn't introduced a show-stopping syntax error. Go ahead and do that now...

Dum...Dee...Dum...

All still works? Good! Still more code needed...

This gets installed right after the `Alien(i)` function's closing bracket `}`
```
/*--------------------------------
   Create all alien sprites.
*/

function makeAliens() { // L12
    var i; // L12
    aliens = [];  // L12
    for (i = 0; i < NUM_ALIENS; i++)  // L12
       aliens.push(Alien(i)); // L12
} //end makeAliens()
```
First, `var i;` declares our loop variable. 

Second, `aliens = [];` initializes the global variable `aliens` to an empty array, ready to receive all our pesky little, bird flippin, laser shooting fershlinger alien space ships...

Next, `for (i = 0; i < NUM_ALIENS; i++)` which loops from zero to `NUM_ALIENS` exclusive, executing this line: 
`aliens.push(Alien(i));` which actually creates the alien ship sprite, and pushes the newly created object onto the end of the `aliens[]` array.

Now, this cutie function doesn't do us any good unless it is actually *called* by our existing code. Care to guess where it is called from?

If you said the `init()` function, you'd be dead on - so go and install this line of code:
```
  makeAliens(); // L12
```
right under the `makeAsteroids();` statement of the `init()` function.

Test your code. Still work ok? But still no aliens? Well, that's to be expected. More code to add...

This function, 
```
/*--------------------------------
   Animate alien sprites.
*/

function updateAliens() { // L12
    var th, i; // L12
    // Loop through all alien ships 
    for (i = 0; i < aliens.length; i++) {  // L12
        // Is alien visible?
        if ((th = aliens[i]).visible) {  // L12  
          // Do alien laser stuff here...
          th.update();  // L12
        }
        else if (th.spawnCnt > 0)  // L12
            th.spawnCnt--; // L12
        else { // L12
            th.show(); // L12;
            th.setDY(0); // L12
            th.setDX(10); // L12
            th.setPosition (50, 50 + 50 * i); // L12 
            th.setBoundAction(DIE); // L12
            th.spawnCntFun (i); // L12
            th.update(); // L12
        }        
    }
}
```
Does a lot of work for us. The purpose of `updateAliens()` is to actually perform all the processing associated with moving our alien ship, *and it's laser* after being fired. (As stated, laser stuff in another lesson)

Fist, `var th, i;` establishes two local working variables: `th` as a convenient object variable, and `i` the loop variable.

Second, `for (i = 0; i < aliens.length; i++) {` should be obvious as a loop construct which iterates over all the sprite objects in the `aliens[]` array.

Third, `if ((th = aliens[i]).visible) {` does two things at once: accesses the sprite object indexed by `i` and saves the reference in `th`, then tests the `visible` property. 

If this sprite *is* visible, there is laser stuff to do, and we need to execute 
`th.update();` to draw the alien sprite on the screen. 

If it *isn't* visible, the following code is executed:
`else if (th.spawnCnt > 0)` to see if the `spawnCnt` property has reached zero; if not, the next line, `th.spawnCnt--;` reduces it's value by one, and we are done with this update code.

If `th.spawnCnt` *is* exhausted, then we need to set up the alien ship to fly across the screen, to wit:

`th.show();` Set the alien sprite `visible` property to true so it shows up on the canvas on the next update cycle.
`th.setDY(0);` Set it's acceleration in the `Y` direction (up & down) 
`th.setDX(10);` ...and in the `X` direction (left & right) to zero. In other words, it will move at a constant speed...
`th.setPosition (50, 50 + 50 * i);` Set it's initial position to a random X,Y position based on its `aliens[]` array index number. It will be positioned 50 pixels to the right, and 50 units down from the last alien, and the top of the screen. 
`th.setBoundAction(DIE);` When the alien reaches the right side of the screen, it automatically gets its `visible` property set false, making it disappear again. 
`th.spawnCntFun (i);` Reset the `spawnCnt` to a new value greater than zero so that when it dies at the end of it's run - or if it gets destroyed by one of our bullets, it will be able to live again... 
`th.update();` And lastly, draw the alien on the screen.

So, check your code. See any aliens? No? But does it still play the way it should otherwise? Good! Because the last thing to do for alien ships to appear is...

Install this line:
```
    updateAliens(); // L12
```

Where? 

Guess what... You get to ponder that until next lesson...

Until then...hide under your bed! The Space Aliens are coming!!!

# Asteroids: Lesson 13
**Standby for Collision!**
Now that we have dreaded alien spaceships flying about in our game, we need to add code to handle collisions with our ship, as well as give ourselves the ability to destroy them with our bullets. 

Believe it or not, this is a pretty simple task, and all the code necessary to do both is already part of our game's code-base - we just need to modify it a bit to handle this new responsibility. 

Consider this code, which comes from the `checkCollisions()` function:
```
  for (i = 0; i < bullets.length; i++) { // L7.1
    // Check for bullet hitting asteroid... // L7.1
    for (j = 0; j < asteroids.length; j++) {  // L7.1
      if (bullets[i].collidesWith(asteroids[j])) { // L7.1
        // bullet-asteroid Collision detected... 
        bullets[i].hide(); // L7.2
        asteroids[j].hide(); // L7.3
        asteroids[j].spawnCnt = Math.floor(30 + Math.random() * 20); // L7.4
        addPoints(asteroids[j].hitPoints); // L8
      }
    }
  }
```
It handles collisions between our bullets and asteroids. Given that we have a neat array of alien spaceships called `aliens[]`, what would we need to add so that it also checks the collisions with alien ships?

```
    // Check for bullet hitting alien....  // L13
    for (j = 0; j < aliens.length; j++) { // L13
      if (bullets[i].collidesWith(aliens[j])) { // L13
        aliens[j].hide(); // L13
        aliens[j].spawnCntFun(j); // L13
        bullets[i].hide(); // L13
        addPoints(SCORE_ALIEN); // L13
      }
    }
```
You can install it just above the comment line, `// Check for bullet hitting asteroid...`

Now, let's analyze it line by line...
`for (i = 0; i < bullets.length; i++) { // L7.1` This is an existing line added clear back in Lesson 7. It sets up a loop which allows us to scan through all bullets in flight to see if one is in collision with something. Previously, we were checking only for asteroid hits, but now, with the additional code below, we also check for collisions with alien ships.

`for (j = 0; j < aliens.length; j++) {` This line sets up a loop to scan through the array of `aliens` to see if the current bullet -  indicated by `bullets[i]` - is in collision with the current alien ship - indicated by `aliens[j]` 

`if (bullets[i].collidesWith(aliens[j])) {` This is a test to see if the current bullet is in collision with the current alien.

`aliens[j].hide();` This - and the following lines - are executed if the current bullet collides with the current alien. This statement hides the alien ship, causing it to no longer be drawn on the canvas upon the next update cycle.

`aliens[j].spawnCntFun(j);` This is a function call to set the respawn counter. Recall that after a predetermined number of update cycles - or frames, if you like - the alien ship will automatically reappear to harass our poor ship again.

`bullets[i].hide();` Alas, only one target per bullet! So, we hide the bullet so that it can be reused. 

`addPoints(SCORE_ALIEN);` Claim a little credit for taking out the alien space invader! `SCORE_ALIEN` will be added to our current score, and the new value displayed to the player.

That's it - now go test your code to see if you can shoot and destroy the alien space invaders. I'll wait...

Dee-Dum-Dee...

Back? So how'd it go? Good! 

Now, at this point, those pesky alien ships aren't much bother - they just fly through the game like sitting ducks! Well, it's time to add the code to make them a little more bothersome.

Here is the new code:
```
  // Check for alien hitting ship L13 or alien laser hitting ship....
  for (i = 0; i < aliens.length; i++) {
    // Check for alien hitting ship - L13
    if (spaceShip.collidesWith(th = aliens[i])) { // L13
      th.hide();  // L13
      th.spawnCntFun(i);  // L13
      die();  // Lose a life...L13
      return; // L13
    } 
    // Check for alien laser hitting ship - L13
  }
```
It can be installed just over the line `} //end checkCollisions()`

Notice the comment, `// Check for alien laser hitting ship` - don't worry about it for now. We'll add that logic later.

So, let's analyze this line by line:

`for (i = 0; i < aliens.length; i++) {` This should be familiar - a loop to go through the alien spaceships looking for collisions.

`if (spaceShip.collidesWith(th = aliens[i])) {` Test to see if the current alien - indicated by `aliens[i]` - is in collision with our ship. If it is, all the following code is executed.

`th.hide();` Hide the alien. If we don't, then we will experience multiple collisions one right after another, until our lives are exhausted. Also, notice that we are not referencing the current alien directly through the array, but using a temporary variable `th` - which we set in the `if()` statement above. This is for convenience.

`th.spawnCntFun(i);` We've also seen this before - set the respawn counter so that our alien nemesis can come back again. 

`die();` Loose a life, and update the score/life counter display for the player.

`return;` At this point, we've already died, so abruptly end the collision detection routine and move on.

As always, test your code. 

Ok, so that's it for this time, Space Cadet! See you next Lesson, where we'll make those pesky space aliens even more deadly by giving them a laser to shoot at us! 