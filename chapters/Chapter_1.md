Chapter 1: Console
==================

###Sections:

* [Meet Our Worker](#meet-our-worker)
* [Boxes and Instructions](#boxes-and-instructions)
* [Introduction to the Console](#introduction-to-the-console)
* [Homework](#homework)

##Meet our Worker

Programming can be thought of as us explaining to an employee what we want them to do. Take for instance handling a Google search for *capital of Canada*. We can imagine Google telling an employee of theirs *'Find out what the capital of Canada is for Jane and return to Jane a list of links that you think are important.'* This analogy seems simplistic but in all actuality this is all programming is: us giving our computer a list of instructions. The problem comes in when we realize how *completely stupid* our computer is. 

Imagine that you are trying to explain to a baby who only understands the words 'yes' and 'no' how to crawl to the refrigerator. Perhaps you come up with some sets of yes's and no's in a certain order that help the baby get to the refrigerator. Now explain to the baby how to get you a Pepsi but only if there are at least 5 Pepsi's or more left because your partner really likes Pepsi and will drink 4 at least once they are home. How difficult would that be? How about telling the baby how to go to Santa Fe and ask Joe for information about his e-commerce website and display them to you in a specific order? 

At the base level our computer, our worker, is that baby. It only understands either yes (`1`) or no (`0`) and we have to find ways to explain abstract ideas like *go to the fridge and grab me a Pepsi* or *ask Joe for information on products* in sequential 1's and 0's. Luckily for us, people far smarter than me have came up with ways to explain to the worker base instructions like `pop`, `push`, and `compare`. With these instructions we can start writing programs that *compile* into the yes's and no's that our worker understands. We start to `abstract` a set of 1s and 0s into the word `pop` so when we tell our worker what to do we can explain it nearly in our native language and have another worker (a `compiler`) make it into instructions that our worker understands. 

Each level of `abstraction` can be thought of as a worker. Each time we get away from `binary`, we are creating an abstraction, creating a new worker that understands new commands that can communicate with the worker below it. Our `assembly` worker can talk to our `hexdec` worker that can talk to our `binary` worker. Our `c` worker can talk to our `assembly` worker. Our `javascript` worker can talk to our `c` worker. Our `react.js` worker can talk to our `javascript` worker. 

Another way to look at it is that anything our `react.js` worker can do, our `javascript` worker can do because our `react.js` worker has to explain to our `javascript` worker what you meant. However not everything our `javascript` worker can do is a command that our `react.js` worker understands. We will see what these words and phrases mean in later chapters but the important thing to notice is that each worker explains the instructions you gave it to the lower worker in the way that the lower worker understands. Just like you explained the instructions to your worker in the way that it understood. 

Since this is a JavaScript book, we can forget about our `c` worker and below. We are only going to focus on how we communicate with our `javascript` worker and how we can give it the correct instructions in a way that it will not only understand but more importantly be able to complete the job in a way that we deem correct. So how do we talk to our worker? What's the language that it understands?

Our worker natively only understands certain words and symbols. [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Lexical_grammar#Keywords) has a nice list of all of the keywords that our worker understands. Everything else that we wish to tell our worker is going to be up to us finding a way to mix and match boxes and instructions built with those keywords in a way that our worker can follow to complete whatever mission we give it. We can think of these keywords as the base `abstraction` of our worker so that instead of our worker only understanding `1` or `0`, it can understand what you mean when you say `do` or `this`. Along with these keywords, our worker understands things called `operators`, like `=`, `+`, and `*`. Once again [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators) has a great list of these. The keywords and operators describe the `language` that our worker understands. But the real question is how do we use these `operators` and `keywords` to explain to our worker what we want it to do?

##Boxes and Instructions

The way that I like to think about how we talk to our worker is through boxes of information and instructions on what to do with that information. For instance, let's suppose that I wanted to tell my worker to follow a map to a location. We can think of a box holding the `map`, some sort of information that we as a human call a map but to our worker it is just a piece of paper in a box that he knows the location of inside of his warehouse. We then have a list of instructions that tell the worker how to follow the map and tell him *"follow these instructions and when I use the word* `map` *I am pointing at the box holding the information that you need."* But how do we tell the worker what the map is or what the instructions are? Let's start coding.

##Introduction to the Console

Open up your browser ( *I'll be using Chrome but very browser has a console.* ) and right-click any window. It should open a menu that has an `inspect` or `Inspect Console` option. That will open up a section that will have a tab called `Console`. Click that and you should have something like the following on your screen:

![Console in the Browser][Image_1]

If you click next to the carat, you can start typing. Let's see how we can add numbers:

```
> 2 + 2
// 4
>
```

Which makes us believe that subtracting numbers would be the same:

```
> 2 - 2
// 0
>
```

But does our worker deal with negative numbers?

```
> 0 - 2
// -2
>
```

What other math operators does our worker know?

```
> 2 * 2
// 4
> 2 / 2
// 1
```

How about the order of operations? Think of how you imagine the worker would do this and why you think they would do it like that:

```
> 2 + 5 * 5
```

What did our worker get? Was it `2 + ( 5 * 5)` or was it `(2 + 5) * 5`? What happens when we actually put those expressions inside of the console? What kind of rules do you think the worker is following to come up with the answer? 


>Coder Break:
>
Throughout this book, I will ask questions and ask you to try things without giving you what the outcome should be or the answer to the question. This is to foster the questioning of why and how things work. While you can just copy/paste from this book, you will gain far more if you take a moment or two after each concept and break it. Finding the edges of the language helps far more than learning the syntax or an API. 


We see that our worker understands what a `number` is and has some basic operations that it can do with them ( `+`, `/`, etc). How about text? Let's see. With numbers we could just type in what we wanted and it understood. Can we just type in some text and our worker understand?

```
> hello world!
// Uncaught SyntaxError: Unexpected identifier
```

_**Uh-oh**_

It seems that when we type in `hello world!`, our worker thinks that is it an `identifier` or a *box's name*. If we want our worker to know that we want the text to be a value ( like `2` is a value ) instead of an `identifier`, we need to express that idea in a specific way to our computer:

```
> 'hello world!'
// "hello world!"
```

There are two other ways to tell our worker that the text is not an `identifier` but a `value`:

By surrounding it with double quotes ( `"..."` )
```
> "hello world!"
// "hello world!"
```

or by surrounding it with the backtick ( `` `...` `` )

```
> `hello world!`
// "hello world!"
```

We won't be using the backticks until we get into template strings so no need to worry about it for now. Just a good little nugget to know when we look at code later.

So we know how to tell our worker that some text is a `value`. How about if we want to put two `strings` together? What if we wanted to take `'hello'` and `'world!'` and make `'hello world!'` out of it? I wonder if we can `add` two strings together.

```
> 'hello' + 'world!'
// "helloworld!"
```
Well. That is kinda what we wanted. We got the `string` values put together but our worker is not smart enough to understand that we wanted a space value between the strings. It looks like we have to be very explicit when we tell our worker what we want it to do. So let's tell the worker to add a space character between `'hello'` and `'world!'`:

```
> 'hello' + ' ' + 'world!'
// "hello world!"
```

I wonder if minus with strings works the same way as it did with numbers:

```
> 'hello world!' - 'world!'
// NaN
```

_**Whoops**_

Our worker is telling us that the `expression` `'hello world!' - 'world!'` results in the value of `NaN` or Not a Number. It appears that our worker has specific things it can and cannot do with a `string` or `number` and that those do not always correspond with the other `type`. We'll get into `types` and what that all means in the next chapter. For now, let's move on to `boxes`!

When we tried to enter in `hello world!` without any quotation marks, our worker told us that it was an `Unexpected identifier` error and I told you that an `identifier` is just the name for a box. So how do we tell our worker the name of a box and what is inside of that box?

```
> const box = 'this is a box!'
// undefined
> box
// "this is a box!"
```

```
Possible Error:

If you get an error where the keyword const is not allowed, update your browser. Seriously.
```

Do not worry about the `undefined` statement. That will become important later but for now it just means that our `assignment` worked. Instead let's think about what is going on here:

1. Our worker creates a box called `box`. He does that because we are using the command `const` which he understands as *I need to create a box and the next group of letters I see after const will be the name of that box.*
2. Our worker `assigns` a `value` to that box. He does that because of the `=` operator. He understands this `expression` as *I need to put the value on the right of the = into the box name that is on the left of the =*.



>Coder Break:
>
There are two other ways to `declare` a variable in JS: `var` and `let`. There are very important differences between what `const`, `let`, and `var` actually do that we will get into later. For now, know that `const` is *kinda* short of `constant` while `let` and `var` are *kinda* the same thing. 
>
Another important thing to understand at this point is that when we `assign` a `value` to a box, the two become equivalent. If we say `const name = 'Timi'`, we are telling our worker *Whenever you see the identifier name, I want you to replace it with the value 'Timi'*. 

When we create boxes or `variables`, we are creating our own custom `abstraction` on top of JavaScript. We are creating a new set of keywords that our worker understands. Let's see what this means. From the previous example of addition with numbers:

```
> 2 + 2
// 4
```

We are telling our worker *Add the value on the left of the `+` operator to the value on the right*. And since boxes are just names for a value, we can do this:

```
> const two = 2
// undefined
> two + two
// 4
```

Our worker follows the same thing as it did with `2 + 2`, except this time instead of the actual value of `2`, we are telling our worker *Look inside of the box labeled `two` and add that value to the value labeled `two`*. I wonder if this works for `string` values as well:

```
> const hello = 'hello'
// undefined
> const world = 'world!'
// undefined
> const helloWorld = hello + ' ' + world
// undefined
> helloWorld
// "hello world!"
```

##Recap

* When we *program*, all we are doing is trying to find a way to explain a set of instructions to our worker.
* Our worker is very, *very* stupid and only understands a few things. It is our job to find a way to explain our instructions using only those few things. 
* Variables are our way of telling our worker *There is a box named x with the value of y*. We build our own `abstraction` using boxes on top of the keywords and expressions that our worker understands in order to explain our instructions in a way that we the developer can understand. 

##Homework:

* Create boxes using `const`, `let`, and `var`. Do they act differently at all right now? What do you think the differences are based on what you see?
* Try `reassigning` a box to a new value:

```
> const name = 'Timi'
// undefined
> name = 'Kristen'
```

  - What does our worker tell us?
  - What happens if you use `let` instead of `const`? How about `var`?
  
* Why do you think when we do addition ( `2 + 2`), we get the value underneath ( `4` ) but when we `assign` a value ( `const name = 'Timi'` ), we get `undefined` instead of `"Timi"`? What is our worker telling us when he says those things?


##Before Moving On:

Before we get into `types` and `instructions`, we really need to have an understanding of `assigning` values. Be sure that you are comfortable with creating boxes and using them to create new boxes ( `cosnt four = two + two` ). Come up with your own analogy of what the computer is doing and how. I will continue using the `boxes and instructions` metaphor but if that doesn't make sense to you, work on creating your own mental idea of what is happening behind the scenes. 

If you are comfortable with all of this and have done your homework, check out [Chapter 2](./Chapter_2.md) and get ready for the serious programming to start!

[Image_1]: ../assets/img/chpt_1_1.png