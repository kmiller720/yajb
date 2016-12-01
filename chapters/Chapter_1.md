Chapter 1: Console
==================

###Sections:

* [Meet Our Worker](#meet-our-worker)
* [Boxes and Instructions](#boxes-and-instructions)
* [Introduction to the Console](#introduction-to-the-console)

##Meet our Worker

Programming can be thought of as us explaining to an employee what we want them to do. Take for instance handling a Google search for *capital of Canada*. We can imagine Google telling an employee of theirs 'Find out what the capital of Canada is for Jane and return to Jane a list of links that you think are important.' This analogy seems simplistic but in all actuality this is all programming is: us giving our computer a list of instructions. The problem comes in when we realize how *completely stupid* our computer is. 

Imagine that you are trying to explain to a baby who only understands the words 'yes' and 'no' how to crawl to the refrigerator. Perhaps you come up with some sets of yes's and no's in a certain order that help the baby get to the refrigerator. Now explain to the baby how to get you a Pepsi but only if there are at least 5 Pepsi's or more left because your partner really likes Pepsi and will drink 4 at least once they are home. How difficult would that be? How about telling the baby how to go to Santa Fe and ask Joe for information about his e-commerce website and display them to you in a specific order? 

At the base level our computer, our worker, is that baby. It only understands either yes (`1`) or no (`0`) and we have to find ways to explain abstract ideas like *go to the fridge and grab me a Pepsi* or *ask Joe for information on products* in sequential 1's and 0's. Luckily for us, people far smarter than me have came up with ways to explain to the worker base instructions like `pop`, `push`, and `compare`. With these instructions we can start writing programs that *compile* into the yes's and no's that our worker understands. We start to `abstract` a set of 1s and 0s into the word `pop` so when we tell our worker what to do we can explain it nearly in our native language and have another worker (a `compiler`) make it into instructions that our worker understands. 

Each level of `abstraction` can be thought of as a worker. Each time we get away from `binary`, we are creating an abstraction, creating a new worker that understands new commands that can communicate with the worker below it. Our `assembly` worker can talk to our `hexdec` worker that can talk to our `binary` worker. Our `c` worker can talk to our `assembly` worker. Our `javascript` worker can talk to our `c` worker. Our `react.js` worker can talk to our `javascript` worker. 

Another way to look at it is that anything our `react.js` worker can do, our `javascript` worker can do because our `react.js` worker has to explain to our `javascript` worker what you meant. However not everything our `javascript` worker can do is a command that our `react.js` worker understands. We might use `onClick={fn}` to explain to our `react.js` worker that we want something to happen, which will tell our `javascript` worker something like `onclick="fn()"`. We will see what these words and phrases mean in later chapters but the important thing to notice is that each worker explains the instructions you gave it to the lower worker in the way that the lower worker understands. Just like you explained the instructions to your worker in the way that it understood. 

Since this is a JavaScript book, we can forget about our `c` worker and below. We are only going to focus on how we communicate with our `javascript` worker and how we can give it the correct instructions in a way that it will not only understand but more importantly be able to complete the job in a way that we deem correct. So how do we talk to our worker? What's the language that it understands?

Our worker natively only understands certain words and symbols. [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Lexical_grammar#Keywords) has a nice list of all of the keywords that our worker understands. Everything else that we wish to tell our worker is going to be up to us finding a way to mix and match boxes and instructions built with those keywords in a way that our worker can follow to complete whatever mission we give it. We can think of these keywords as the base `abstraction` of our worker so that instead of our worker only understanding `1` or `0`, it can understand what you mean when you say `do` or `this`. Along with these keywords, our worker understands things called `operators`, like `=`, `+`, and `*`. Once again [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Expressions_and_Operators) has a great list of these. The keywords and operators describe the `language` that our worker understands. But the real question is how do we use these `operators` and `keywords` to explain to our worker what we want it to do?

##Boxes and Instructions




##Introduction to the Console