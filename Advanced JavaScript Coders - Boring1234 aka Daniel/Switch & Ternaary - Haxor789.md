Extended version of this:
http://www.codecademy.com/de/forum_questions/52373a75548c3515940000dc

 - Control Flow  Part 2

- switch-case statement
- Ternary operators

Now that we know about the if-else-else conditional statement which is a rather general tool to handle different cases let's come to a more specific one. If you have one variable/value and want to branch out depending on the value of this variable you can use switch. Switch may sound like On/Off but it can handle far more then just 2 states.

The general syntax of switch is:

    switch(variable/value){
        case value1: statements
        case value2: statements
        case value3: statements
        ...
    }

and it takes the varaible/value and compares it to the values mentioned after a **case** keyword and if it finds a matching one it will execute everything that follows after the `:`. 

The good thing: there can be statements without having to use {}.
The bad thing: it will also execute the statements of the following cases. So in
order to prevent this we need to end our statements with a `break;`, this will cause the switch to stop and we continue after the } of the switch. 

But that isn't so bad at all, because it also enables us to execute more than one case if needed e.g.

    switch(day){
       case "Monday": getFood();
       case "Tuesday": 
       case "Wednesday": 
       case "Thursday": 
       case "Friday": goToWork(); break;
       case "Saturday":
       case "Sunday": relaxItsWeekend(); break;
    }

Here from Monday to Friday `goToWork()` is executed but e.g. on Monday `getFood()` is executed too.

*But why did You mentioned value aswell and not only variable?*

Well another nice way of using the switch statement is that you could also use e.g.

    switch(true){
       case condition: statements break;
       case condition: ...
       ...
    }

where the case is chosen for which the condition is true. Also you could use a string in switch and ask via a prompt for each case, but be carefull, switch compares type and value so using numbers and prompt won't work as prompt returns strings. 

And last but not least switch also has its optional else statement which is named `default:` anything which occurs after default is executed if the switch had not been **break**-ed before.

The last in the row of conditional statements mentioned above is the Ternary operator, which is just a shorter form for if-else:

    condition?statement1:statement2;

It goes like this :

    Is the condition true? Yes do this : No do that

Examples could be (1):

    var name = (sex == "male")?"John Doe":"Jane Doe";

aswell as (2):

    weather == "good"?goOut():stayInside(); 


as you can see this is nice for making a short inline check but although you can nest it, it is almost inevitable to create code that no human being could read without wasting more precious lifetime than necessary e.g.

    condition1?condition2?case1:case2:condition3?case3:case4

if you want to use them at all cost for this purpose at least use () to show which cases belong together:

    condition1?(condition2?case1:case2):(condition3?case3:case4)

and as whitespaces are mostly ignored also try to stretch it to e.g.:

    condition?(
        condition2?(
            case1
        ):(
            case2
        )
    ):(
        condition3?(
            case3
        ):(
            case4
        )
    )

Which becomes something similar to nested if/else conditionals and can aswell be improved by writing it in an if/else if/else style:

    condition?(                   //if
        case1
    ):(condition2?(               // else if
        case2
    ):(                           // else
        case3
    )

As we now have more space to write, we can talk about using mulitiple statements in a case. To do so we use the [**comma operator**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Comma_Operator) which means we simply seperate our statements with a comma `,`. e.g.

    condition?(
        statement1,
        statement2,
        statement3
    ):(
        statement4,
        statement5
    )

*One last question: "What is the value of a case with multiple statements, as we saw in (2) that you can use ternaries to assign values aswell?"*

Well the comma is a binary operator (*), which is interpreted from left to right and it's value is the value of the second argument e.g. `statement1, statement2` would have the value of statement2.

So if we have this:

    statement1 , statement2 , statement3 , statement4

the interpreter would interprete it like this:

    ((statement1 , statement2) , statement3) , statement4

and then evaluate each of these pair from left to right:

    statement1 , statement2
     --> statement2
    (statement1 , statement2) , statement3
     ---> statement2 ,statement3
    --> statement3
    ((statement1 , statement2) , statement3) , statement4
    ---> statement3 , statement4
    ---> statement4

Summary: So no matter how many statements you connect with the comma operator the value of the whole statement is always the value of the last statement.


(*) This simply means it expects 2 values around it

[Return To Master Menu](http://www.codecademy.com/groups/advanced-javascript-coders/discussions/53307af3631fe9e8de00103b#discussion-53307af3631fe9e8de00103b)