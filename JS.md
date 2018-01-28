# All About JavaScript
##### A. What is JavaScript?
***Ans.*** 
1. It is the most commonly used client side scripting language. 
2. It was created by Brendan Eich.
3. It is more of a scripting language then a programming language as over here it manipulate browser to do all the dirty work.
4. All the interaction, notifications that pop up, beautiful games (except flash games which are dying away everyday) are designed in JavaScript. 

***What JavaScript can't do:***
- JavaScript can't read or write file systems.
- JavaScript cannot execute any other programs
- JavaScript cannot establish any connection to any computer unless it is a request made to that computer to download HTML pages or to send an email.
 
***JavaScript is Async:***
One more important thing to note about JavaScript is that it is asynchronous in nature. That is there is no guarantee which part of the code is going to execute first and which part later. Suppose there is a code that interacts with the server in the backend and the code needs to wait untill it returns a result, the great thing about this language is that it won't wait. It will keep on executing other parts of the code and when the result has arrived from the backend it will catch the event and do the required things upon receiving it.

***JavaScript is loosely typed language:***
 Loose typing means that variables are declared without a type. This is in contrast to ***strongly/statically typed*** languages that require typed declarations. Consider the following examples:
 ```js
 /* JavaScript Example (loose typing) */
var a = 13; // Number declaration
var b = "thirteen"; // String declaration

/* Java Example (strong typing) */
int a = 13; // int declaration
String b = "thirteen"; // String declaration
 ```
 By not declaring typed in javascript, that doesn't mean JavaScript is not typed, they are typed internally whenever they were assigned a value.
 "Loosely typed" means language does not bother with types too much, and does conversions automatically, i.e. you can easily add string to an integer and get the result as a string whereas "Dynamically typed language" on the other hand means that you do not need to declare variable type (and in most cases variable itself) before use.
> JavaScript is both dynamically and loosely typed language.

***Type Coercion:***
Type coercion is a topic that is closely associated with loose typing. Since data types are managed internally, types are often converted internally as well. Understanding the rules of type coercion is extremely important. Consider the following expressions, and make sure you understand them:
```js
7 + 7 + 7; // = 21
7 + 7 + "7"; // = 147
"7" + 7 + 7; // = 777
```
In the examples above, arithmetic is carried out as normal (left to right) until a String is encountered. From that point forward, all entities are converted to a String and then concatenated.
