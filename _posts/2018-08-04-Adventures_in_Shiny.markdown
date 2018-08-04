---
title: 'Adventures in Shiny'
layout: post
published: true
categories: R Shiny
tags: R Shiny
---

# Synopsis
Adventures in the Shiny web framework for R

# Printing text
verbatimTextOutput(id)  print the *contents* of the reactive *variable* whose name is `id`
p(text) print the *literal* *static* text `text`

# Modularizing code
When using Shiny modules (highly recommended, to avoid cluttering the global namespace!), there
are a couple of things to consider:
- always use ns(id) in your submodules to generate consistent and unique names

