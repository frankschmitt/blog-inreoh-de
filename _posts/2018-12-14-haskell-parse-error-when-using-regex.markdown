---
title: 'Parse error on input \'{\' when using regular expressions'
layout: post
published: false
categories: haskell regex
tags: haskell regex
---

# Synopsis
While trying to solve #4 for the Advent of Code 2018, I ran into a strange error when 
using the literal form for a regex:

```
Solve.hs:63:46: parse error on input ‘{’
```

The offending line was:
```
  where regex = [re|${y}([0-9]{4})-${m}([0-9]{2})-${d}([0-9]{2})|]
```

The (at least to me) strange thing was that this line was perfectly fine when
I put it into a separate source file. Turns out that the compiler directive

```
{-# LANGUAGE QuasiQuotes                      #-}
```

has to come *before* the module declaration in the source file. Swapping the
ordering of the compiler directive and the module declaration solved the problem.
