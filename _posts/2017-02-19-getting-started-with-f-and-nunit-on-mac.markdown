---
layout: post
title: Getting started with F# and NUnit on Mac OS X
date: '2017-02-19T08:27:00.000-08:00'
author: Frank Schmitt
tags: 
modified_time: '2017-02-19T08:27:14.130-08:00'
blogger_id: tag:blogger.com,1999:blog-6373343020354235841.post-3409315213340295611
blogger_orig_url: http://inreoh.blogspot.com/2017/02/getting-started-with-f-and-nunit-on-mac.html
---

# Synopsis 
F# has long been on the list of programming languages I wanted to try, and now I've finally gotten around to do it.  

# Installation  
## Using Docker 
```docker pull fsharp/fsharp```
See https://hub.docker.com/r/fsharp/fsharp/ for additional information.  

## Using Home
```
brew brew install mono
```

# Setting up a simple project 
We're using Visual Studio Code here and use http://www.davesquared.net/2013/03/hello-world-testing-in-fsharp.html as a starting point.  
## Create the SUT assembly 
Contrary to best (TDD) practices, we're going to create the "production" code first (for now).  
  - create a new F# project (type: library, name: HelloWorld2, dir: HelloWorld2) 
  - replace HelloWorld2.fs with this:  namespace HelloWorld2  module Math =    let add x y = x + y  
  - compile it using      fsharpc -a -o bin/Debug/HelloWorld2.dll HelloWorld2.fs  

## Create the test assembly 
  - create a new F# project (type: F# test, name: HelloWorld2_test, dir: HelloWorld2_test 
  - replace HelloWorld2_test.fs with this:  module HelloWorld2_Test  open NUnit.Framework open FsUnit open HelloWorld2  [<Test>] let exampleTest () =     Assert.AreEqual(2, MyMath.add(1,1))   
  - compile it using fsharpc -a -o bin/Debug/HelloWorld2_Test.dll -r ../../packages/NUnit/lib/net45/nunit.framework.dll -r ../../packages/FsUnit/lib/net45/FsUnit.NUnit.dll -r ../../HelloWorld2/HelloWorld2/bin/Debug/HelloWorld2.dll HelloWorld2_Test.fs  - run it using (DOES NOT WORK) nunit-console bin/Debug/HelloWorld2_Test.dll  ../../packages/NUnit/lib/net45/nunit.framework.dll ../../packages/FsUnit/lib/net45/FsUnit.NUnit.dll ../../HelloWorld2/HelloWorld2/bin/Debug/HelloWorld2.dll   
