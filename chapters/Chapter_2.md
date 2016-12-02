Chapter 2: It Begins
====================

###Sections:

* [What's in a Name?](#whats-in-a-name)
* [Is it Equal or Similar?](#is-it-equal-or-similar)
* [Homework](#homework)

##What's in a Name

If you remember from Chapter 1, I said that our worker only understands the reserved keywords and operators. That's not completely true. As we saw, the worker also understands what the number `2` is along with what a string is ( *as long as we put '', "", or `` around it!* ). That is because JavaScript has a few different `types` of data that is understands natively. There are 7 different `types` of data that JavaScript understands, grouped together under either *primitives* and *object*. 

###Primitives

The *primitives* types are:

* `Boolean`
* `Null`
* `Undefined`
* `Number`
* `String`
* `Symbol`

We won't get into Symbol so we can just pretend that it's not a thing right now. When we say `primitive`, we do not mean to say that they are less important than `objects`. What we mean when we say `primitive` is that these values are an exact unit. We can never change what our worker thinks `2` is. It will always be `2`. While we can change what value we place inside of our boxes, we cannot tell our working *Treat the number 2 as if it were the number 4* 

Just like we saw with `numbers` being able to have certain operations performed on them ( `2 + 2` ) and `strings` have the same `operator` being used ( `'hello' + ' ' + 'world!'` ), it does not mean that they perform the same action or that both types have the same operations available to them ( `'hello world' - 'world'` *is not valid* ). Each `type` has certain operators that they work with and certain places where we would want to use them.

> Coder Break:
>
Primitives are `immutable` data: they can never be mutated. This idea of `immutability` will become a cornerstone as we reach into functional programming ideas but for now we can just think of a primitive as a value that can never be different than what it is. This is not to be confused to a box always being a value. We are saying that `2` will always and forever be `2`


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

The values `null` and `undefined` are very similar in that they represent a void value (a non-value). However, the distinction is that `null` means that the box has been set to `null` while `undefined` could mean that the box was never defined, nothing was returned, or that you set it to be that value. We assign it just like everything else:

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


##Is it Equal or Similar

##Homework