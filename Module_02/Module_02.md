# Module 2

## It's All About Types

Functions, Methods, and Values, oh my! 

Module 2 will focus on higher order functions. We saw a _very_ brief introduction to this concept in [module 1](../Module_01/Module_01.md#higher-order-functions). This section we'll dive deeper into HOF and see how useful they really can be. 


## Terminology 

Before we dive into all this, we should become familiar with some terminology.

**Function** (In the conventional generic programming sense): A named set of instructions. Just like the mathematical function, i.e: `f(x) = x + 1`

<br />

**Function Literal** much like a string literal (i.e `"Hello world"`) is the portion defining the function:
```scala
List(1,2,3).map(x => x * 2)

// `x => x * 2` is the function literal 
``` 
<br />

**Method** (In the conventional generic programming sense): a named set of instructions associated with an object. I.e, a function tied to an object. 

<br />

**Predicate** ([obligatory Schoolhouse Rock video](https://www.youtube.com/watch?v=ODj-T1vzy2E)) a function that returns a Boolean. It's easy to think about this in terms of SQL:

```SQL
SELECT * FROM table WHERE column = 1
```
The `WHERE column = 1` is a predicate, and returns rows that only hold true. 

<br />

## Types


## Functional Vals & Defs

So remember when we went over the function vs method terminology? That was in the traditional generic programing language sense (i.e, C++, Java, etc). In Scala, functions and methods are a wee bit different. 

The most general way of creating a function is with the `def` keyword:
```scala
def petCat(): Purrs => {...}
```

Surprise!   In Scala That's actually a _method_.

The way to create a "function" is via the `val` keyword, and a function literal:
```scala
val scratchHuman = (numberOfPets: Int) => numberOfPets != 3
```

For non cat owners:

<img src="https://pbs.twimg.com/media/DKxUmWTUQAApmZs?format=jpg&name=large" width=70%/>

<br />

Side by side:
```scala
def isEvenMethod(i: Int) = i % 2 == 0         // a method
val isEvenFunction = (i: Int) => i % 2 == 0   // a function
```

But wait, I know for a **fact** (because I read the docs 🤓 ) that something like the `.map()` method takes a _function_ not another method. And you're right! it does. So how does that work? Through a process called [ETA Expansion](https://docs.scala-lang.org/scala3/book/fun-eta-expansion.html).  Scala's compiler implicitly converts a method to a function (Using traits like `Function1`, `Function2`, etc. More on traits later). 

Okay cool, that's something new. But should I _really_ care?

No. You you have my permission to forget about this if you want.  


Additional Readings:
* https://alvinalexander.com/scala/fp-book/how-to-use-scala-methods-like-functions/


## Exercises

### Write a filter function:
```

def filter() => {

}