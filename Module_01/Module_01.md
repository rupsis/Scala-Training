# Module 01
## < Working Title > FP: The Separation of Church and State

If you like math (and don't lie to me, I know which ones of you are Data Scientists) you'll probably love functional programing. 

---

If that's not enough to convince you, lets take a simple problem: 
```
Given a List of numbers [n_1 ... n] filter to only even numbers
```

Easy enough. So here's how you'd do it in an imperative language (C++, Java, Etc)

```scala 
val source: List[Int] = List.range(0, 10) 
var destination: List[Int] = List()

for(i <- 0 to source.length - 1 ){
    if(source(i) % 2 == 0){
        destination = destination + List(source(i))
    }
}
```

Okay, not _too_ bad. But here's the functional way:

```scala
val destination = List.range(0, 10).filter(_ % 2 == 0)
```

Boom! Done. 

The author provides a free sample of the [Functional Programming Simplified](https://alvinalexander.com/downloads/fpsimplified-free-preview.pdf) book which is suffice for the readings in this module. But I highly recommend getting yourself a copy. 

**Note**: The text and PDF number counts don't line up, and my E-reader formats the PDF a _little_ weird. So the page number references will be for the PDF version of the book with a page number `+/- 3` (σ = 3 for my stat nerds) depending on where you're reading it (E-book reader, computer, etc). 

Also! here is a fun little Scala function you can use to _map_ the PDF page number to the book page number:

```scala
// Again, result is +/- 3 pages from what I'm referring too
def bookPageNum(pdfPageNum: Int): Int = {
    (pdfPageNum / 0.6627f).round
}
```

I'll try my best to include page titles, heading, etc to help with the page difference. 

## Readings:
* What does functional programing mean?
* Arguments for FP
* 

---

## What is a _Pure_ Function? 

Suggested reading:
- Pg 124 - 139 (Definition of "pure function" & Grandma's cookies)
- Pg 147 -  (Benefits of pure functions, )

Simply put: A function whose output is dependant on the input with no side effects. 

This is analogous to a math function:
```
f(x) = x + 1
f(2) // 3
f(10) // 11
```
The math function `f(x)` is pure. Output is dependent on the input with no side effects. 

If, for example. the math function where:
```
f(x) = x * 2 && Launch missiles
f(2) // 4 and some destruction... I.e side effect
```

##### Optional Readings:
- ##### The Red Book: Chapter 1 Listing 1.1

--- 
## What is immutability?
> "My wife isn't just stubborn, she's immutable" - Me

Immutable means it doesn't change. 

Simple math example:

```
immutable:
    x = 3
    y = x + 2 // y = 5

```
We can be confident that `y` will always be 5, since `x` can't change. Whereas: 

```
mutable:
    x = 3
    y = x + 2 // y = 5
    x = 4
    x = -1
    ... etc
```
`y` is now all over the place, and the only determining factor for `y` is the point in time of the computation of `x`. This gets extremely difficult when you introduce parallelism. 

> "Non-determinism = parallel processing + mutable state" - Martin Odersky (Scala creator)

In Scala, we can declare mutable and immutable variables:
```scala
val a = 'a' // immutable variable a

a = 'b' // Nope! can't do that. 

// ---- 

var a = 'a' // mutable variable a

a = 'b' // it works! and everyone got confused. 
```

## Higher order functions
A language feature that treats functions like types. 

Again here is a math example (you seeing a pattern?):
```
// simple math function
a(x) = x + 1

// Intersting...
y = a(x) 

b(z) = z * 2

f_2(y(1)) -> 
```

## Recursion






## Functors
<small>reading: Pg 112 - 118 _"A short excursion to ... The Twilight Zone_</small>

Things that can be mapped over.  

A things that a function can be applied too? 

Funky Actors... Functors? 

## Combinator
~~The love child of combos and terminator~~ A chain of functions. 



Can easily be thought of like a Unix pipeline:
```bash
command | anotherCommand -with - flag | finalCommand > file.txt
```


From [Wikipedia](https://en.wikipedia.org/wiki/Combinatory_logic): 
> A combinator is a higher-order function that uses only function application and earlier defined combinators to define a result from its arguments.

## Additional Reading / Resources
- [Functors, Applicatives, And Monads In Pictures](https://adit.io/posts/2013-04-17-functors,_applicatives,_and_monads_in_pictures.html)

## Random terminology tid bits
Generally λ (lambda) in terms of modern programs, mean "Anonymous function". Or a function with no name. Kinda like a horse with no name, but makes for a less catchy song. 

`Expressions` are bits of codes that return values

`Statements` are bit of codes that do not necessarily return code, but generally modify state. 

Example:
```scala
// an example of an expression. It returns a value  
val lunchTimeBeverage = if(isFriday) "Beer" else "Water"

// this is an example of a statement. 
if(wifeIsntHome()){
    cookiesEaten = cookiesEaten + 1
}

```