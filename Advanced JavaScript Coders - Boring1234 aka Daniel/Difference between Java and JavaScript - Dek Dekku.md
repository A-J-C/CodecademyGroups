Java implements the classic OOP paradigm using classes and interfaces, while JavaScript has prototypal inheritance. The `new` keyword has been introduced to make it look like Java, but it doesn't really work the way a Java/C#/C++ programmer would expect (and let's not talk about the `this` keyword...) and you're better off not using it.

Java is a static language: once created, an object retains its type for all its lifecycle: you can't add new methods, you can't add new fields, just change their values. JavaScript is dynamic, you can do whatever you want with an object since there's no explicit mention of its type anywhere in the language.

Java is a strongly typed language: variables have a type too, and it must be declared when you create each one of them. A variable can only reference objects of the same (or compatible) type. In Javascript typing is loose, and variables are just references to an object: their type is defined by the properties of the object they reference, and therefore it can change at runtime.

For the two previous reasons, Java is compiled only while JavaScript is an interpreted language (even though JS compilers do exist.) A nice consequence is that you almost never have type errors in Java at runtime: they are detected at compile time (in fact, most IDEs detect them while you write your code), or better at linking time, when the parts that compose your application are brought together.

On the other hand, JavaScript has no concept of linking whatsoever. A consequence of this is that it strongly relies on global variables. While Java strongly disallows their use.

(Technically speaking, there are no global variables in Java, just instance fields and local variables, and there are no functions, just methods.)

Also, in JavaScript functions are objects and you pass them around all the time, and in fact functional programming is the true nature of language, hidden under the C-like imperative syntax. In Java you can only pass objects: if a method needs to pass a function to another method, they must agree on an interface that will become the type of an object in which that function will be incapsulated. That object will then be passed around.

Java has native support for binary data (as almost any other language) while JS is still lacking (it will be introduced in ECMAScript 6). Java has native support for multithreading, while JS doesn't, even though the WebWorker has been introduced as an API in HTML5, therefore you can implement threads using the service offered by the browser, but it's not a feature of the language itself.

And there's more I guess...