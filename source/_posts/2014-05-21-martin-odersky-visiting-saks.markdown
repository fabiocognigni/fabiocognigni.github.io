---
layout: post
title: "Q&A with Martin Odersky at HBC Digital"
date: 2014-05-21 10:15:06 -0400
author: Fabero
comments: true
categories: Scala

---

Big day here at HBC Digital: we hosted a Q&A session with Martin Odersky at our offices in NYC.
When you have only one hour you have to choose really well the questions to ask among the hundreds you would have.
An important thing to keep in mind is that you are not talking with another web developer but with a "compiler guy" (as he defined himself). Indeed as you probably know already he wrote the compilers for modula 2, modula 3 ... up to the javac Java compiler before writing Scala.
More in general it is quite impressive how he was able to apply a solid academic analysis approach to real industrial problems.

I think we did a pretty good job in using that limited amount of time driving the discussion on "hot" topics like coding philosophies, functional and object-oriented programming coexistence, comparisons with other emerging languages, Java 8 and performances.

Personally I didn't resist the temptation to use this occasion in the most constructive way: not celebrating things I like in **Scala** but pointing out perplexities and limits around it.

Here a summary of the conversation.

<!--more-->

### Functional and OO programming: do they make sense together?

The first question was about my perplexities on the coexistence between **functional** and **object-oriented** programming. On one side functions and **immutability** drives you on the correct direction of keeping less state as possible and avoid side effects, on the other a construct like an object that implicitly, silently and constantly brings you to tend recreating the same issues. His answer still didn't convince me 100% but it makes sense: the object constructs help you organize your software in modules (but is this so much different from a namespace of pure functions?) to better handle the complexity of **large systems**.

### Scala performances

My second question was around the well-know pain point of Scala: **performances**! I asked what exactly are the technical reasons that make the Scala compiler not that performant and I also asked for tips (if any!) around writing Scala functional code able to perform well at runtime.
His answer for the compiler performances was an incredibly interesting trip under the hood: cool Scala features like **type inference**, **implicits**, **closures** are objectively and inevitably expensive for the compiler that needs to resolve to the appropriate type (or value in the case of closures) in scope. He also pointed out that **compiler** performances have been already improved a lot recently and this optimization is still a big priority including incremental compilation. Regarding runtime performances some tips are again the same you should have been using since you were a Java programmer: e.g. use arrays and primitive types when possible - **boxing**/**unboxing** are not cheap operations. The other tips are more Scala/functional specific: use always **tail recursion** when possible (and help the compiler with @tailrec annotation) and take advantage from the fact that in a world of functions you can do lot of caching.

### Scala (not so simple) type system

Another interesting and prickly question was around the fact that Scala is supposed to simplify coding through immutability and functional support but it has aspects that makes it not that simple: first of all its **super detailed type system**. It was also mentioned the project Dotty. He admits that the Scala type system is not small but he argued that having specialized types has obvious advantages and helps even more in the direction of type safety.

### Scala compared with other functional languages

Dr. Odersky was then inquired regarding comparison with languages like **Clojure**: in here he mentioned again the importance of having object-oriented approach to have an easier modularization and have a **static typing** to have the compiler doing type checking and introduce as less errors as possible at runtime.

### Coding styles

I liked also the discussion around the fact that currently it's hard to find in all the Scala code that you can read around a prevalent **style of coding**. This might be due to two factors in his opinion (totally agreed): the most obvious that is still a "young" language that looks really intriguing but it also take a while to be mastered. The second factor is that it leaves the programmer a broad horizon of choices given its mixed nature object-oriented/functional.

### Scala and Java 8

The last point I want to report is his opinion about the fact that Java is finally moving in the direction Scala took long time ago, mainly for its support of **lambda expressions** and how the paths of Java and Scala will proceed in the long term. After joking on the fact that as of now almost only C++ was the language with no lambda expression other than Java, he pointed out how still Scala has a lot bigger conceptual space than lambda expressions mentioning the fact that in Scala **functions** have a **type**, Scala has **implicits**, multiple inheritance with mixin **traits**, **pattern matching** with **case classes**, etc. He also explained that according to the current roadmap a full support of Java 8 should be implemented in around one year (with Scala 2.12) even if probably Scala will maintain its own syntax for lambda expressions but overall performances will improve and their integration work Scala-Java will be much easier.


These were just some highlights of a very interesting discussion that was an extremely useful checkpoint of where we are in this JVM ecosystem and what are the possible lines of evolutions for the future.

Things like this definitely **makes your day**!
