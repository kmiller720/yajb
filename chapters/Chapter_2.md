Chapter 2: It Begins
====================

###Sections:

* [What's in a Name?](#whats-in-a-name)
* [Is it Equal or Similar?](#is-it-equal-or-similar)
* [Homework](#homework)

##What's in a Name

If you remember from Chapter 1, I said that our worker only understands the reserved keywords and operators. That's not completely true. As we saw, the worker also understands what the number `2` is along with what a string is ( *as long as we put '', "", or `` around it!* ). That is because JavaScript has a few different `types` of data that it understands natively. There are 7 different `types` of data that JavaScript understands, grouped together under *primitives* and *object*. 

###Primitives

The *primitive* types are:

* `Boolean`
* `Null`
* `Undefined`
* `Number`
* `String`
* `Symbol`

We won't get into Symbol so we can just pretend that it's not a thing right now. When we say `primitive`, we do not mean to say that they are less important than `objects`. What we mean when we say `primitive` is that these values are an exact unit. We can never change what our worker thinks `2` is. It will always be `2`. While we can change what value we place inside of our boxes, we cannot tell our worker *Treat the number 2 as if it were the number 4* 

Just like we saw with `numbers` being able to have certain operations performed on them ( `2 + 2` ) and `strings` have the same `operator` being used ( `'hello' + ' ' + 'world!'` ), it does not mean that they perform the same action or that both types have the same operations available to them ( `'hello world' - 'world'` *is not valid* ). Each `type` has certain operators that they work with and certain places where we would want to use them.

> Coder Break:
>
Primitives are `immutable` data: they can never be mutated. This idea of `immutability` will become a cornerstone as we reach functional programming ideas but for now we can just think of a primitive as a value that can never be different than what it is. This is not to be confused to a box always being a value. We are saying that `2` will always and forever be `2`.
>
We can also think of primitives as values that the computer understands while objects are user-created values that boil down into primitives.
>
**Primitives are boxes that our worker controls and that we can only access**


_**Boolean**_

A Boolean value can be either `true` or `false`.

```
> const isTimiCool = true
// undefined
> isTimiCool
// true
> const isWorkingFun = false
// undefined
> isWorkingFun
// false
```

Notice how there are no quotation marks around `true` or `false`. That is because, just like `2`, our worker understands what the value `true` means. If we put quotation marks around true, like `'true'`, we would be telling our worker *Here is a string with the characters `t`,`r`,`u`, and `e`*. Which is not what we are meaning to tell him at all. There have been many wasted hours in my own past projects where a value was `'true'` and not `true` and I couldn't figure out why it wasn't working!

_**Null & Undefined**_

The values `null` and `undefined` are very similar to each other in that they represent a non-value. However, the distinction is that `null` means that the box has been set to `null` while `undefined` could mean that the box was never defined, nothing was returned, or that you set it to be that value. We assign it just like everything else:

```
> const definedButNull = null
// undefined
> definedButNull
// null
const definedButUndefined = undefined
// undefined
> definedButUndefined
// undefined
> let declaredButNeverAssigned
// undefined
> declaredButNeverAssigned
// undefined
```

You will notice that I am using `let` to declare `declaredButNeverAssigned`. Can you find out why?

>Coder Break:
>
You might notice that each time we `assign` a value to a box, our worker prints out `undefined` underneath it. That is because the `assignment operation`, the `const box = value` line, is equivalent to the value `undefined` just like `2 + 2` is equivalent to `4` or `'hello ' + 'world!'` is equivalent to `'hello world!'`. 

###Objects

> Coder Break:
>
The other `type` in JavaScript, `object`, is a difficult type to explain. There is an in-depth definition that explains how everything in JavaScript is an object, even the `object literal`. This definition is a little too confusing when we are first learning so we are going to have to come up with a not-technically-valid definition for what an `object` is. At least for now.

We can think of an `object` as a custom `type`. If we cannot express our data through `primitives`, we can create a data structure using an `object`. It will eventually have to be primitive values but we can structure it however we wish, if it's valid syntax. Let's see what I mean.

Suppose we want to have a `user` with a `name` and an `age`. We could have the following:

```
const name = 'Timi'
const age = 28
```

Now if we ever want to get the name of this user, we can tell our worker to get the `name` box. This works and everyone is happy for awhile. But what if there are two users in the same area of code? How can we differentiate between userA's name and userB's name? We could create two `name` boxes, `nameA` and `nameB`, and then reference them. Or we could use an object to `encapsulate` the `name` and `age` boxes. We create boxes within a box for our worker to keep track of using `key/value` pairs:


```
const user = {
  name: 'Timi',
  age: 28
}
```

Just like before, we are `declaring` a box, called `user` here, and `assigning` that box the value of the `object` `{name: 'Timi', age: 28}`. The curly braces ( `{` and `}` ) are just our way of telling our worker that this is a grouping of things. The information between the curly brackets in an `object` assignment are the key/value pairs that we want this object to have. We can imagine that the keys (`name` and `age`) are boxes attached to the bigger box `user` and their value is what is between the colon and the comma (`'Timi'` and `28`). 

What we are telling our worker with the above assignment is:

*Hey, here is a box called `user`. I want you to create two boxes inside of that box. Call one `name` and set this string, `'Timi'`, as its value. Call the other `age` and set this number, `28`, as its value*

Because that is what we told our worker, when we tell the worker to grab us the value `user`, we are given the whole object as the return value. What if I wanted to get just the `name` from the `user` object? How do we reference a box inside of a box? Well, like most things in JavaScript, there are more than one ways to do that. 

The first way is through `dot notation`. We can just reference the `key` or `property` of the `object` that we want and our worker will either return the value or `undefined` if we have not declared it yet:

```
const name = user.name
// name is set to 'Timi'
```

If we tried to get an unset property:

```
const url = user.url
// url is set to undefined
```

Using `dot notation`, we can also `assign` values to inner boxes:

```
user.name = 'John'
const name = user.name
// name is set to 'John'
```

If there is already a value there, the new value that we are `assigning` will override the previous value as we are seeing above. If there is not a property already set, our worker creates one:

```
user.url = 'https://github.com/beardedtim'
const url = user.url
// url is set to 'https://githube.com/beardedtim'
```

> Coder Break:
>
You might be noticing that we declared user as a `const` and we are reassigning/changing values without any errors. This is because `const` doesn't **actually** mean constant. It really means that we cannot change the reference for the variable. Because we are referencing a box ( `object` ), our worker doesn't actually change what it is referencing but rather changes the values inside of that reference. Basically when we declare a `primitive` with `const`, we can never change it (because they are immutable). When we declare an `object` with `const`, we can change the inner boxes with no problem but can never change the `type` that the `object` is. We can set `user.name` but cannot `user = 'Timi'` because we would be pointer our worker at a new box!

The other way to access keys from an object is through `bracket notation`, where instead of doing `object.name`, we do `object['name']`. Notice how `name` in the first one, `object.name`, is an `identifier` while in the second ,`object['name']`, it is a string. This concept will come in handy later but knowing it now will help us from making a simple mistake:

```
object[name] 
```

is not the same as:

```
object['name']
```

Think on why that is. It will become very important later.

Let's say that instead of `key/value` pairs, we need just a simple list of values. We are not worried about getting `object.name` but instead are wanting to get a value at an `index`, like the 3rd value in the list. Given our object idea, let's see if we can create something.

```
const list = []
```

An `array` is just a list of values. In JavaScript it doesn't matter what those values are or if they are the say `type`. And we access the contents very similarly to how we access an `object`:

```
const list = []
list[0] = 'Timi' // ['Timi']
```

The `indexes` start at `0`.

**Go more in-depth here about arrays**

##Is it Equal or Similar

We have seen that to `assign` a value to a box (`variable`), we use the equal sign, `=`. This is our way of telling our worker to do the `assignment operation`. But what if we wanted to ask our worker if something is equivalent to something else? How can we check `equality` if the equal sign is used for assignment instead? 

Just like before, our worker understands certain symbols in a certain order to `mean` something. He knows that `=` means `assign the value on the right side to the box on the left`. He knows that `2 + 2` means `add the value 2 to the value 2` (4) and that `'hello ' + 'world!'` means `add the value 'world!' to the value 'hello '` ('hello world!'). He also knows what `==` and `===` mean. Let's see what he thinks those symbols together mean.

###Strictly Equals

When our worker encounters `===`, he assumes we are telling him *Tell me if the value on the left is absolutely equal to the value on the right*. In practice, let's see what that looks like:

[Link To See](https://jsfiddle.net/aqg4hzbc/2/)
```
2 === 2
// true
'Timi' === 'Timi'
// true
'Timi' === 'timi'
// false 
true === true
// true
true === false
// false
null === null
// true
undefined === undefined
// true
undefined === null
// false
```

We notice that for the `primitive` values, strictly equals (`===`) works exactly how we want it to. The string `'Timi'` is of course equal to the string `'Timi'` and `true` is of course equal to `true`. The weird part comes into play when we try to compare objects:

```
{name: 'Timi'} === {name: 'Timi'}
// false
[1,2,3] === [1,2,3]
// false
```

Our worker is telling us that objects with the exact same values are not equal to each other, which is not intuitively what I would have imagined. Let's think about why this is.

Above we mentioned that our worker understands the values of `primitive` types. It has a box somewhere in its memory labeled `value_for_integer_2` or something to that affect, and when we check if `2 === 2`, it compares your value against its value and says *Yup, these two boxes are exactly the same value*.

This concept is the reason why when you declare a `const` as a `primitive`, you can never change it: these values have a place in the workers brain and you can't just change it without getting inside and getting inside is far past the scope of this book. 

How about an `object`? What happens when we declare `const obj = {}`? Can we change what is held inside of that like `obj.name = 'Timi'`? I bet you these objects not being able to be easily compared has something to do with this concept. Can you find out why? Look at the `object` section's *Coder Break* to see more information if you can't come up with an answer yourself. 

###Equal Objects

So is there any way our worker will return `true` when comparing objects? Well of course, but only if they are _**actually equal**_:

```
const user = {name: 'Timi'}
user === user
// true
```

And this makes sense because we are asking our worker *Does the box in my hand equal the box in my hand?* Of course the same box is equal to the same box. How about the below:

```
const user = {name: 'Timi'}
const otherUserBox = user
otherUserBox === user
// ?
```

Does this expression equal `true` or `false`? Let's walk through what we are telling our worker line by line:

1. *I have a custom data type I want you to create a box for*
2. *I want you to point this other box to the previous box*
3. *Are these two values both pointing at the same box?*

> Coder Break:
>
If you are coming to JavaScript from another language, you might have this idea of `reference` vs `value` and `pointers`. While I say that our worker is *pointing* at something I am not meaning in the literal CS way of a `pointer`. I am meaning that an object is just a reference to some values and that we can pass that reference around. 

To fully understand why `otherUserBox === user`, we need to have some sort of idea of what our worker is doing when we create non-primitive boxes. 

Like I said before, any value that is not a `primitive` is an `object`. This is because all an `object` really does is offer you an interface to get to `primitive` values. For instance:

```
const user = {name: 'Timi'}
```

Here, the primitive value is `'Timi'`. Our computer understands that `'Timi'` is a string, therefore it has some idea of what that value equals. What the `object` does is gives us a way to reference this `primitive` value later. Our worker has created a place in its warehouse and labeled it `user`, which has a smaller box called `name`. 

When we pass around the box `user`, our worker is not passing around the boxes inside of it ( *the actual value of the box* ) but instead just passes us the `reference` to the box `user`. This is because our worker doesn't understand the values inside of the box because they are not `primitive`. `name` is an `identifier`, not a `primitive`. 

Let's take a look at this concept from a different perspective. 

Everyone has a street address. This is a unique identifier, a unique set of characters in a specific order, that tell the postman how to deliver a letter to the correct house. The postman does not know what is inside of the house nor cares. All he knows is that when someone puts *1234 Main St*, they mean this specific mailbox. 

Now imagine that the city changes the address from *1234 Main St* to *4321 Washington Ave* and we want to get our mail copied from *1234 Main St* to this new address as well. You want to change the `reference` the postman has for where you live. You have not changed, just what is written on the letter.

You go to the post office and say *I can now also be reached at 4321 Washington Ave* and from that point until you tell them otherwise, they will assume that any time a letter goes to *1234 Main St* or to *4321 Washington Ave*, it is a letter for you and finds where you are and delivers your Amazon packages. 

When we create an `object`, we are telling our postman the address to some thing. We are giving the worker a `reference` to a house. When we change what we call that, when we change the address of the `reference`, we do not change what it is pointing at ( *you do not change when you move houses* ) but rather how we reference it. 
 
The next question is: what happens when the values that you are referencing changes? If you are the owner of both *1234 Main St* and *4231 Washington Ave* and you eat a sandwich at *1234 Main St*, did the owner of *4321 Washington Ave* also eat a sandwich? If *1234 Main St* and *4321 Washington Ave* both point at the same house, and you change the bathroom color of *4321 Washington Ave*, did the color of the bathroom inside of *1234 Main St* also change?

> Coder Break:
>
This is not that big of a thing to know right now but in the next chapter or two we will see how vitally important this concept is. Take some time now and find the edges. This will come back and bite you in the butt if you don't. 

##Homework






