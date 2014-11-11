We're going to continue our theme of lists this week. Browsing the Q&A forum, I found a lot of people having issues with list iteration and understanding when and how to iterate them. In Python the best way for list iteration is to use a `for` loop. Although a `while` loop would also work, it requires more care on your behalf and more memory/code. Here's a brief example:

You have a list of Python dictionaries corresponding to different students in a class. Each dictionary looks as follows:

    Dustin = {
        "name" : "Dustin",
        "homework" : [100 98 97 95 97],
        "quizzes" : [100 103 96 89],
        "tests" : [99 97 92]
    }

So your `students` list would be defined as `students = [Dustin, Charles, Michael, Joah, Dory, Linda, Sasha, Leng, Eric, Adam]` (assuming we have all these students and their respective dictionaries). Now, we could try and calculate the averages of each person's quizzes by hand but that would take extraordinarily too long. The better approach is to write a function that takes in the student's dictionary and returns the average of whatever score you're looking for. An example of this method would be:

    def averageHomework(student):
        return sum(student['homework'])/len(student['homework'])

I would like to note that this isn't the best approach or best method. This is only an example for teaching purposes. So let's now say we would want to take the average of each student's homework. The incorrect approach would be:

    averageHomework(students)

Our function can't operate on lists so this approach won't work. Hence, we need to iterate our list and pass one student at a time. One way is the `while` loop which would look like:

    i = 0
    num_of_students = len(students)
    while i < num_of_students:
        print averageHomework(students[i])
        i += 1

This approach works but we have to take care of few things: (1) we need to create a iterator variable `i`, (2) we need to set the maximum length of iteration, (3) we have to make sure we increment our iterator, and (4) we have to be careful of accessing the `students` list correctly or our code will error out with a `Bad reference` error. The safer and more efficient way to write the above is with a `for` loop. It looks as follows:

    for student in students:
        print averageHomework(student)

WOW! That's a lot less code. Let's walk through this super quick. The `for` loop says assign a student's dictionary to the placeholder student then print the result from calling `averageHomework` on it. So it would start iterating on `Dustin` then move to `Charles` then `Michael` and so forth and so on. Pretty cool right? This also makes it so you don't need those two extra variables, conditional statement or incrementation step.

That's it for this week. If you would like to contribute to these reviews, please feel free to shoot me an email at sharocko@gmail.com. I'd love to hear your feedback or have you share some input. And as always, please ask questions!