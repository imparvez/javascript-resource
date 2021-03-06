# All About JavaScript
***What is JavaScript?***
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


***Window and Document in JavaScript:***
`window` is the main JavaScript object root aka the global object in a browser, also can be treated as the root of the document object model. You can access it as `window` in most of the cases (in the browser).
`window.screen` is a small information object about physical screen dimensions.
`window.document` or just `document` is the main object of the visible (or better yet: rendered) document object model/DOM.
-  `window` is the execution context and global object for that context's JS. It represents the browser window
- `document` contains the HTML. It represents the HTML document loaded in that window.

***JavaScript is Async and single threaded. Explain***
***What is thread***: a thread is a simple flow of instruction.
An application can be single threaded (so imagine it as a single line going from the entry point of the application to its end) or multi-threaded (imagine a tree: the whole app starts from 1 point, than it branches out more and more).

***Difference between single and multi thread programming paradigm:***
| Multithreaded  | Single Threaded |
| ------ | ------ |
|In this type of programming multiple threads run at the same time | run at the same time. In this type of programming a single thread runs at a time. |
| Multi threaded model doesn’t use event loop with polling | Single threaded model uses a process event loop with polling |
| CPU time is never wasted. | CPU time is wasted. |
| Idle time is minimum. | Idle time is more. |
| It results in more efficient programs. | It results in less efficient programs.|
| When one thread is paused due to some reason, other threads run as normal. | 	When one thread is paused, the system waits until this thread is resumed. |

JavaScript is single threaded. That means our JavaScript code runs into a single threaded event loop at browser end(Each browser window has only one javascript thread running inside them). What makes its async is browser's event loop. Under the hood, the browser code is running multiple threads to capture event queue and then that event loop, in which your code is running gets triggered and it handles the request.
