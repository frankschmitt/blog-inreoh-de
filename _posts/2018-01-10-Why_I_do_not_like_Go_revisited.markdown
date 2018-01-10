---
title: 'Why I do not like Go - revisited'
layout: post
categories: development rant
tags: code development Go programming
---

# Synopsis
I've recently played a little bit with Go (solved one of the Advent of Code puzzles in it - another Blog post with details regarding that will follow soon), and overall, I don't like it. I don't like its attitude, and I don't like the lack of convenience features I expect from newly designed languages nowadays.

This is an updated version written because @inge4pres pointed out on Twitter that the original version of this post was merely a rant without any hard facts.

Disclaimer: As you probably have guessed, I'm a Go beginner - however, I've got 10+ years of professional programming experience.

# The good
## Formatting
One of the (few) things I like about Go is that it brings its own formatting tool along and that there's zero room for configuring it. So no discussions about formatting, braces style etc. 

# The bad
## Testing
Apparently, Go's default testing package doesn't provide ExpectEquals and similar. 

Taken from https://golang.org/doc/code.html#Testing (official Go documentation):

```
    got := Reverse(c.in)
    if got != c.want {
      t.Errorf("Reverse(%q) == %q, want %q", c.in, got, c.want)
    }
```

Seriously? You recommend I *manually compose my assertion and error message* when I want to write a trivial unit test?

What was so wrong about

```
  AssertEquals(Reverse(c.in), c.want, "Reverse does not work as expected")
```

The reasoning seems to be "assertions are bad, therefore we don't use them". While I get why you wouldn't want to have an assert() *macro* in your language, an assert() *test assertion* surely will hurt no one?
Sure, I can easily roll my own testing package, but that kind of defeats the purpose of a default package, doesn't it?

## Tooling (or lack thereof)
- REPL: Go doesn't provide a REPL out-of-the-box (although 3rd party solutions / add-ons exist)
- Build tool: the *go* executable has a *build* command, but this apparently doesn't provide dependency handling (*dep* seems to be the official *experiment* for handling dependencies)
- semantic versioning: Go doesn't provide semantic versioning (which makes sense, since it has no official dependency management tool)

## Missing / incomplete language features 
- Go provides only minimal type inference  
- Go has no standard tuple type  
- Go has no destructuring assignment (which makes sense, since it also has no tuple type)
- Go has no case *expression*, it only has case *statements*
- Go has no generics. Unofficial advice: "Consider copy & paste" or "Use a code generator" (https://appliedgo.net/generics/). That's insane.
  Java started without Generics, but they noticed that they're incredibly useful, and therefore added them later on. For Go (which was created *after* this change)
  to omit Generics *on purpose* seems an insane design decision to me.

Especially in comparison to other (relatively) new programming languages (Swift, Rust, Kotlin, Crystal), Go's type system and language constructs seem quite poor.

# The ugly (personal opinion + experience)
## Naming
* Choosing Go as the name of a new programming language was incredibly stupid (since Go the board game has been around for thousands of years). Searching for "Go tutorial" can therefore never be unambiguous - either you want an explanation of the board game, or you want one for the programming language. But apparently, Google's arrogance let them assume that they don't have to respect anybody else.
* Similarly, Goroutines is a silly name that leads to endless confusion with the well-established term coroutines. The fact that goroutines are *similar* to coroutines
*but also different* (see http://www.golangpatterns.info/concurrency/coroutines ) makes this even worse.

## Attitude of the Go core team
At first, I thought "Ok, Go is still young, and they made some mistakes that they will certainly fix in future releases". But then, I read this: 

"There are many things in the Go language and libraries that differ from modern practices, simply because we feel it's sometimes worth trying a different approach. https://golang.org/doc/faq#assertions
"

To me, this translates to: "We do it differently because we are Google and therefore know better than everybody else on the planet. We ignore important research and knowledge obtained by others because we massively suffer from the NIH syndrome."

## Attitude of Go users
The final straw was the attitude that several Go users showed on StackOverflow, e.g. 

 "It's not the Go way" https://stackoverflow.com/a/18638071/610979  

It might not be the Go way, but it's the *sensible, industry proven* way. 

# Conclusion
Go seems useless to me. It would have been a great language if it had been invented in the '80s, and it would have been ok in the '90s. But in the 21st century, its lack of features is appalling (esp. compared to Rust, Crystal etc.)

Goodbye, Go. I wish you all the best.

 

 
